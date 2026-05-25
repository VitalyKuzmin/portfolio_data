# Руководство по созданию MCP-плагинов

## 1. Введение в MCP

**Model-Component Protocol (MCP)** — это протокол, который позволяет внешним, независимым процессам (плагинам) взаимодействовать с основным приложением. Это ключевая часть архитектуры, обеспечивающая модульность, безопасность и расширяемость.

**Преимущества MCP-плагинов:**
- **Изоляция:** Каждый плагин работает в своем собственном процессе, поэтому ошибка в одном плагине не приведет к сбою всего приложения.
- **Независимость зависимостей:** Плагины могут иметь свой собственный набор библиотек и зависимостей, не конфликтуя с основным приложением.
- **Полиязычность:** Плагин может быть написан на любом языке, который поддерживает взаимодействие через `stdio` или `http`.

## 2. Типы плагинов

Существует три основных типа плагинов, которые вы можете создать:

### Инструменты (`tools`)
Это действия, которые AI-агент может выполнять. Они, в свою очередь, делятся на два подтипа, определяемых в `manifest.json`:
- **`"usage_type": "tool"` (Основной инструмент):** Мощное действие, которое агент может вызывать напрямую. Примеры: `run_ui_scenario`, `web_search`.
- **`"usage_type": "utility"` (Утилита):** Вспомогательная функция, доступная только из `PythonCodeExecutor` через объект `computer`. Пример: `computer.browser.open_url(...)`.

### Снэпшоты (`snapshots`)
Это плагины, которые собирают данные о состоянии системы "по запросу". Например, получение URL текущей активной вкладки браузера. Результат работы снэпшота добавляется в общий контекст, который передается агенту.

### Наблюдатели (`watchers`)
Это долгоживущие фоновые процессы, которые отслеживают активность пользователя (например, активное окно, нажатия клавиш). Они обычно отправляют данные в `ActivityWatch` для последующего анализа.

## 3. Структура плагина

Каждый MCP-плагин должен иметь следующую структуру папок:

```
my_awesome_plugin/
├── manifest.json         # Обязательно: описывает плагин
├── server.py             # Точка входа (может называться иначе)
├── requirements.txt      # Опционально: зависимости Python
└── settings.json         # Опционально: настройки для UI
```

### `manifest.json`
Это "паспорт" вашего плагина.

```json
{
  "id": "my-awesome-plugin",
  "type": "tool",
  "name": "My Awesome Plugin",
  "description": "This plugin does something awesome.",
  "version": "1.0.0",
  "entry": "server.py",
  "usage_type": "tool"
}
```
- `id`: Уникальный идентификатор (должен совпадать с именем папки).
- `type`: Тип плагина (`tool`, `snapshot` или `watcher`).
- `name`: Человекочитаемое имя.
- `entry`: Файл, который будет запущен.
- `usage_type` (только для `type: "tool"`): `tool` или `utility`.

### `settings.json`
Этот файл позволяет добавить настраиваемые параметры для вашего плагина, которые появятся в UI настроек.

```json
{
  "settings": [
    {
      "key": "api_key",
      "label": "API Key",
      "type": "text",
      "default": "",
      "description": "Your API key for the awesome service."
    },
    {
      "key": "max_results",
      "label": "Max Results",
      "type": "number",
      "default": 10
    },
    {
      "key": "enable_feature_x",
      "label": "Enable Feature X",
      "type": "boolean",
      "default": true
    }
  ]
}
```
Поддерживаемые типы полей: `text`, `number`, `boolean`, `select` и специальный тип `neuron_selector`.

### `server.py` (Точка входа)
Это основной код вашего плагина. Рекомендуется использовать библиотеку `fastmcp` для легкого создания MCP-сервера.

```python
from fastmcp import FastMCP

# Создаем MCP-сервер с уникальным именем
mcp = FastMCP("MyAwesomePluginServer")

@mcp.tool()
def do_something(param1: str) -> str:
    """Это описание появится в промпте агента."""
    # Здесь ваша логика
    return f"Something was done with {param1}"

if __name__ == "__main__":
    # Запускаем сервер для общения через stdio
    mcp.run(transport="stdio")
```

## 4. Регистрация плагина

Чтобы приложение "увидело" ваш плагин, его нужно зарегистрировать в одном из конфигурационных файлов в `Backend/hai_mcp/manager/`:
- `mcp_tools.json`
- `mcp_snapshots.json`
- `mcp_watchers.json`

Пример записи для `mcp_tools.json`:
```json
{
  "mcpServers": {
    "my-awesome-plugin": {
      "enabled": true,
      "transport": "stdio",
      "command": "${PYTHON_EXECUTABLE}",
      "args": ["-m", "path.to.your.plugin.server"],
      "cwd": "path/to/your/plugin"
    }
  }
}
```
- `my-awesome-plugin`: Ключ должен совпадать с `id` из `manifest.json`.
- `command`: `${PYTHON_EXECUTABLE}` автоматически подставит путь к Python из текущего окружения.
- `args`: Аргументы для запуска. Если ваш плагин — это модуль, используйте `-m`.
- `cwd`: Рабочая директория для запуска.

## 5. Использование Core-сервисов и Нейронов

Ваш плагин может использовать централизованные сервисы, предоставляемые ядром приложения (`hai-core`), включая **Нейроны** (AI-модели). Это позволяет вам, например, вызывать любую LLM, настроенную пользователем, не зная ее API и не имея доступа к ключам.

### Как использовать Нейроны

1.  **Объявите потребность в `settings.json`:**
    Добавьте поле типа `neuron_selector`, чтобы пользователь мог выбрать нейрон для вашего плагина в UI.

    ```json
    {
      "settings": [
        {
          "key": "agent",
          "label": "Agent for my plugin",
          "type": "neuron_selector",
          "neuron_type": "text_to_text"
        }
      ]
    }
    ```
    - `neuron_type`: Фильтрует список нейронов. Возможные значения: `text_to_text`, `text_image_to_text`, `computer_vision`, `audio_to_text`, `text_to_audio`.

2.  **Вызовите нейрон из кода:**
    В коде вашего плагина вам нужно будет получить настройки и вызвать `core_neurons_call`.

    ```python
    from fastmcp.client import Client
    import os

    # URL менеджера передается через переменные окружения
    manager_url = os.environ.get("MCP_MANAGER_URL")
    if not manager_url:
        raise RuntimeError("MCP_MANAGER_URL is not set")

    mcp_client = Client(url=manager_url)

    def get_my_plugin_settings():
        """
        Эта функция должна получить настройки вашего плагина.
        Один из способов - сделать еще один MCP-вызов к `core_settings_get`.
        """
        try:
            # Получаем все настройки для нашего плагина
            # Замените 'my-awesome-plugin' и 'tools' на ваши значения
            response = mcp_client.call(
                "hai-core_core_settings_get",
                {"key": "plugins_settings.tools.my-awesome-plugin"}
            )
            return response.get("structuredContent", {}).get("value", {})
        except Exception as e:
            print(f"Error getting plugin settings: {e}")
            return {}

    def run_logic_with_neuron(user_prompt: str):
        settings = get_my_plugin_settings()
        
        # 'agent' - это ключ из вашего settings.json
        neuron_config = settings.get("agent")

        if not neuron_config:
            return "Error: Neuron is not configured for this plugin."

        # Вызов нейрона через hai-core
        result = mcp_client.call(
            "hai-core_core_neurons_call",
            {
                "neuron_config": neuron_config,
                "prompt": user_prompt
            }
        )
        
        # Ответ будет в structuredContent
        return result.get("structuredContent")
    ```

### Другие Core-сервисы
Аналогично вы можете вызывать и другие сервисы `hai-core`:
- `core_store_put` / `core_store_get`: для работы с хранилищем.
- `core_rag_query`: для поиска по базе знаний.
- `core_snapshots_list` / `core_snapshots_call`: для получения системных снэпшотов.

Полный список доступен в `Backend/hai_mcp/core/README.md`.
