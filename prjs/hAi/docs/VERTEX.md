Ниже пошаговая инструкция, как подключить aider к новому аккаунту Google Cloud через Vertex AI.
Сделай именно в этом порядке — это закрывает все типичные 403-ошибки.

⸻

1️⃣ Найди Project ID в Google Cloud Console
	1.	Перейди в Google Cloud Console → Home.
	2.	В верхней синей шапке, слева от названия проекта, есть выпадающий список.
Там будут:
	•	Project name – имя (произвольное).
	•	Project ID – то, что нужно (например: named-container-468809-p8).
Скопируй Project ID.

⸻

2️⃣ Включи нужные API

Убедись, что включены:
	•	Vertex AI API
	•	Generative Language API (Gemini API)

В консоли: APIs & Services → Library, в поиске включи оба сервиса.

⸻

3️⃣ Привяжи свой локальный gcloud к этому проекту

В терминале:

gcloud auth application-default login       # войди под своей почтой Google
gcloud config set project <PROJECT_ID>      # тот Project ID, что скопировал
gcloud auth application-default set-quota-project <PROJECT_ID>

Это важно: aider использует Application Default Credentials (ADC).

⸻

4️⃣ Дай себе права на предсказания

В консоли: IAM & Admin → IAM
Добавь для своего пользователя (почты, под которой логинился) роли:
	•	Vertex AI User (roles/aiplatform.user)
	•	Service Usage Consumer (roles/serviceusage.serviceUsageConsumer)

Сохрани.
Если нет прав добавлять роли — это должен сделать владелец проекта.

⸻

5️⃣ Создай/обнови .env

В корне проекта (где запускаешь aider):

VERTEXAI_PROJECT=<PROJECT_ID>
VERTEXAI_LOCATION=global        # или us-central1 / europe-west4

global – самый простой старт, позже можешь выбрать регион.

⸻

6️⃣ Настрой aider

В файле .aider.conf.yml (если его нет — создай):

model: vertex_ai/gemini-2.5-pro
weak-model: vertex_ai/gemini-2.5-flash
timeout: 60

Запуск:

aider --model vertex_ai/gemini-2.5-pro


⸻

7️⃣ Проверка

Быстрый REST-тест:

curl -s -o /dev/null -w "%{http_code}\n" \
 -H "Authorization: Bearer $(gcloud auth application-default print-access-token)" \
 "https://global-aiplatform.googleapis.com/v1/projects/<PROJECT_ID>/locations/global/publishers/google/models"

200 → всё готово.

⸻

Итого
	1.	Скопировал Project ID.
	2.	Включил Vertex AI + Gemini API.
	3.	Настроил gcloud auth и quota-project.
	4.	Выдал роли Vertex AI User и Service Usage Consumer.
	5.	Заполнил .env и .aider.conf.yml.

После этих шагов aider будет стабильно работать через Vertex AI.