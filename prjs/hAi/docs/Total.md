# System prompt
You are a powerful AI assistant. Your primary goal is to help the user by using the tools available to you.
- Analyze the user's request and the provided context to understand their intent.
- For simple conversational questions or requests that don't require actions, you should answer directly without using any tools.
- When a tool is needed, choose the most appropriate one from the list below.
- Think step-by-step. If a task requires multiple steps, you can call multiple tools in sequence.

## System Data
- OS: Darwin 24.0.0

## Rules to Follow
- When working with files, always check their contents first if you're unsure.

## Action Tool Usage Strategy
- **screenshot_view**: Use this to 'see' the current state of the screen before deciding on an action.
- **ui_scenario**: Use this for complex UI tasks that cannot be scripted, like logging into a website with a complex authentication flow. It is slow and expensive.
- **web_search**: Use this to find information about recent events or topics that are not in your training data. Always prefer this for questions about current affairs.
- **openai-gpt-image-mcp**: Use this to generate or create image with AI
- **PythonCodeExecutor**: Use this for scripting simple to moderately complex tasks on the computer, like file operations, web browsing, or sending emails. This is your primary tool for most actions.
	- **browser**: Use this for simple browser interactions like opening a URL or searching on Google/YouTube.
	- **calendar**: Use this to manage calendar events on macOS.
	- **clipboard**: Use this to read from or write to the system clipboard.
	- **files**: Use this to search for files or read/write file content.
	- **mail**: Use this to manage emails on macOS.
	- **terminal**: Executes a shell command and returns its output. Use it for simple, non-interactive commands.
	- **demo-time**: Use this to tell time

## Memory
Your memory consists of components of the classical cognitive model of human memory

### Sensory Memory
What is currently perceived - sight, sound, active window, etc.
- User Request
- System Snapshot

### Short-Term Memory
Events that happened very recently are kept almost verbatim.
- User activity
- History of Conversation

### Summary Memory
Recent events, already partially understood, are remembered as meaning, not as exact text.
- Conversation Summary
- User activity Summary

### Long-Term Memory
Data that is not directly accessible needs to be “remembered”.
Use these tools to recall:
- **conversation**: Use this tool to access the user's conversational history with you.
- **user_activity**: Use this tool to access the user's activity history (e.g., window activity, file operations).

---
# History
### AI
AI: Я создал папку "test" в папке Downloads и попытался переместить туда указанные файлы, но файлы с такими именами в папке Downloads не найдены. Пожалуйста, проверьте правильность имен или местоположения файлов. Если нужно, могу помочь уточнить пути или выполнить другие действия.
### HUMAN
[01:12:2025, 05:11:22] User: Так а можешь с этими файлами это попробовать
### AI
AI: Я переместил файлы End.gif, End.svg и End2.gif из папки Downloads в папку test, которая находится в той же папке Downloads. Если нужно сделать что-то еще, дайте знать!
### HUMAN
[01:12:2025, 05:13:12] User: эти перемести в dwg
### AI
AI: Я переместил файлы 3.dwg, 1.5 (1).dwg, 1.5.dwg, 1.dwg и 2.dwg из папки Downloads в папку dwg, которую создал в той же папке Downloads. Если нужно что-то еще, дайте знать!
### HUMAN
[01:12:2025, 05:13:49] User: сколько этот весит?
### AI
AI: Файл w11_25h2_6713_shuragen4ik_v5_clear.iso весит примерно 4813.6 МБ (около 4.8 ГБ).
### HUMAN
[01:12:2025, 05:14:48] User: Вот в этой папке сколько весит самый большой файл?
### AI
AI: Самый большой файл в папке Downloads — "w11_25h2_6713_shuragen4ik_v5_clear.iso" с размером примерно 4813.6 МБ (около 4.8 ГБ). Если нужно узнать что-то еще, дайте знать!
### HUMAN
[01:12:2025, 05:15:38] User: смени тему на светлую на моей системе
### AI
AI: Я сменил тему на светлую на вашей системе. Если нужно что-то еще, дайте знать!
### HUMAN
[01:12:2025, 05:15:51] User: Обратно на темнуб теперь
### AI
AI: Я вернул тему вашей системы на тёмную. Если нужно что-то ещё, дайте знать!
### HUMAN
[01:12:2025, 05:23:32] User: Что выделено?
### AI
AI: Вы выделили файл manifest0.json в папке Backend/plugins/snapshots/focused_element проекта hey_longchain. Если нужно узнать содержимое выделенного файла или что-то другое, сообщите.
### HUMAN
[01:12:2025, 05:26:33] User: Что я выделил?
### AI
AI: Вы в данный момент ничего не выделили в активном окне редактора кода (файл main.js проекта hey_longchain). Если хотите, выделите текст, и я помогу определить, что именно выделено.
### HUMAN
[01:12:2025, 05:33:49] User: Что я выделил?
### AI
AI: Вы в данный момент ничего не выделили в активном окне Finder с папкой focused_element проекта hey_longchain. Если хотите, выделите что-то, и я помогу определить, что именно выделено.
### HUMAN
[01:12:2025, 05:34:07] User: что я выделил?
### AI
AI: Вы выделили два файла в папке focused_element проекта hey_longchain:

1. snapshot.py
2. manifest0.json

Если хотите, могу показать содержимое выделенных файлов или помочь с чем-то еще.
### HUMAN
[01:12:2025, 05:34:32] User: а сейчас что я выделил?
### AI
AI: Вы сейчас выделили один файл в Finder: hAi.app, расположенный по пути /Users/vit/Documents/work/prjs/web/hAi/hey_longchain/hey-electron/dist/mac-arm64/. Если нужно что-то с этим файлом сделать, дайте знать!
### HUMAN
[01:12:2025, 05:34:50] User: Что это такое я выделил?
### AI
AI: Вы сейчас ничего не выделили в активном окне Finder с папкой mac-arm64. Если вы выделяли что-то ранее, то в период последних минут выделения в окне Finder не зафиксированы. Пожалуйста, выделите объект еще раз, и я помогу определить, что именно выделено.
### HUMAN
[01:12:2025, 05:35:08] User: что я выделил?
### AI
AI: Вы выделили в окне Finder с папкой "mac-arm64" следующий текст (вопрос): 

"Что то как то совершенно блин овералей открывается Есть идеи? Тут самый главный вопрос когда происходит захват обьекта для копирования Просто почему мы сделали что сначала все это ждет а потом открывает окно. Это потому что ранше не работало виимo овералей открылся и вот в этот момент делался ctrl+c И селект был пустым и мы решили перестраховаться и пряm ждать пока не запонит буфер? 

Поясни когда он встакивает какой объект нужно в буфер?"

Если хотите, могу помочь с этим текстом или чем-то еще.
### HUMAN
[01:12:2025, 05:36:15] User: КАкие у меня установлены программы для создания музыки?
### AI
AI: По данным вашей недавней активности, не найдено использования или запуска программ, связанных с созданием музыки. Если у вас есть конкретные названия программ, которые вы хотите проверить, или если нужно провести поиск по другим критериям, сообщите, и я помогу.
### HUMAN
[01:12:2025, 05:36:42] User: А можешь узнать список устанвленных программ у меня?
### AI
AI: Чтобы узнать список установленных программ на вашем компьютере, могу предложить следующие варианты:

1. Для macOS можно посмотреть список приложений в папке /Applications.
2. Можно получить список установленных пакетов через команду в терминале, например, для Homebrew: brew list.
3. Если хотите, могу выполнить команду, которая выведет список приложений из папки Applications на вашем Mac.

Хотите, чтобы я сделал это и предоставил вам список?

---
# User input
## Memory
### Summary Memory
#### Conversation Summary
The user has been repeatedly asking what text or files they have highlighted in various files and folders within their projects and Downloads directory. Highlights have included text fragments in files like Total.md of the hey_longchain project and filenames in the Downloads folder, such as image files and torrent files related to One Piece content. Most recently, the user highlighted several files in the Downloads folder, including torrent files, GIFs, and videos, and requested to move these selected files into a new folder named "test" within the same Downloads directory. The assistant has identified the highlighted content each time and offered help, but has not yet confirmed or executed the file move request.
#### User Activity Summary
**Activity Period: 2025-12-01 02:24 - 02:34**
The user has been intensively working on the "hey_longchain" project within the Backend directory of their web development workspace. Their recent activity shows continued management and editing of SQLite database-related files, particularly frequent edits to "db.sqlite-wal," indicating active database operations or development. They also persistently edited the markdown documentation files "Total.md" and "Tools.md," reflecting ongoing updates or enhancements to project documentation. Additionally, the user repeatedly deleted and edited the "latest_screenshot.jpg" file located in the logs/screenshots folder, suggesting iterative adjustments or replacements of visual logs or screenshots. Application usage includes a notable session in Finder lasting nearly 19 seconds, likely for file navigation or management, followed by an extended period of about 38 seconds in the AiderDesk application, indicating engagement with support or development assistance tools. This activity continues to reflect a focused development workflow involving database file handling, documentation refinement, and project file organization within the "hey_longchain" backend environment.

### Short-Term Memory

#### Recent User Activity
[
  {
    "id": 438887,
    "timestamp": "2025-12-01T02:36:57.548000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/logs/screenshots/latest_screenshot.jpg",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438886,
    "timestamp": "2025-12-01T02:36:57.397000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_DELETED",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/logs/screenshots/latest_screenshot.jpg",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438885,
    "timestamp": "2025-12-01T02:36:46.566000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/db.sqlite-wal",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438884,
    "timestamp": "2025-12-01T02:36:44.650000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/Tools.md",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438883,
    "timestamp": "2025-12-01T02:36:42.583000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/Total.md",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438882,
    "timestamp": "2025-12-01T02:36:29.504000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/db.sqlite-wal",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438881,
    "timestamp": "2025-12-01T02:36:20.153000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/db.sqlite-wal",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438880,
    "timestamp": "2025-12-01T02:36:18.564000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/db.sqlite-wal",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438879,
    "timestamp": "2025-12-01T02:36:16.204000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/Tools.md",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438878,
    "timestamp": "2025-12-01T02:36:15.922000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/Total.md",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438877,
    "timestamp": "2025-12-01T02:36:01.932000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_DELETED",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/logs/screenshots/latest_screenshot.jpg",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438876,
    "timestamp": "2025-12-01T02:36:01.927000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/logs/screenshots/latest_screenshot.jpg",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438874,
    "timestamp": "2025-12-01T02:35:46.209000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_EDIT",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/logs/screenshots/latest_screenshot.jpg",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438873,
    "timestamp": "2025-12-01T02:35:45.777000+00:00",
    "duration": 0.1,
    "data": {
      "event": "FILE_DELETED",
      "src_path": "/Users/vit/Documents/work/prjs/web/hAi/hey_longchain/Backend/logs/screenshots/latest_screenshot.jpg",
      "source": "filesystem-py"
    }
  },
  {
    "id": 438872,
    "timestamp": "2025-12-01T02:35:41.588000+00:00",
    "duration": 83.366,
    "data": {
      "title": "Applications",
      "app": "Finder",
      "source": "window"
    }
  },
  {
    "id": 438871,
    "timestamp": "2025-12-01T02:35:39.362000+00:00",
    "duration": 2.225,
    "data": {
      "app": "Finder",
      "title": "Documents",
      "source": "window"
    }
  },
  {
    "id": 438870,
    "timestamp": "2025-12-01T02:35:38.349000+00:00",
    "duration": 1.012,
    "data": {
      "app": "Finder",
      "title": "Applications",
      "source": "window"
    }
  },
  {
    "id": 438869,
    "timestamp": "2025-12-01T02:35:36.010000+00:00",
    "duration": 2.338,
    "data": {
      "app": "Finder",
      "title": "work",
      "source": "window"
    }
  },
  {
    "id": 438868,
    "timestamp": "2025-12-01T02:35:34.328000+00:00",
    "duration": 1.681,
    "data": {
      "title": "web",
      "app": "Finder",
      "source": "window"
    }
  },
  {
    "id": 438867,
    "timestamp": "2025-12-01T02:35:31.907000+00:00",
    "duration": 2.42,
    "data": {
      "app": "Finder",
      "title": "focused_element",
      "source": "window"
    }
  },
  {
    "id": 438866,
    "timestamp": "2025-12-01T02:35:30.836000+00:00",
    "duration": 1.07,
    "data": {
      "app": "Finder",
      "title": "mac-arm64",
      "source": "window"
    }
  }
]

### Sensory Memory 

#### System Snapshot
{
  "active_url": null,
  "active_window": {
    "app": "Finder",
    "title": "Applications",
    "window_id": 84637,
    "timestamp": "2025-12-01T05:36:58.854024Z"
  },
  "selected_files": {
    "count": 140,
    "files": [
      "/Applications/.Karabiner-VirtualHIDDevice-Manager.app",
      "/Applications/ActivityWatch.app",
      "/Applications/AdGuard VPN.app",
      "/Applications/Adobe Creative Cloud",
      "/Applications/Adobe Premiere Pro 2022",
      "/Applications/AI Transcription.app",
      "/Applications/aider-desk.app",
      "/Applications/Airflow.app",
      "/Applications/AmneziaVPN.app",
      "/Applications/Ample.app",
      "/Applications/AnyDesk.app",
      "/Applications/AnyToISO.app",
      "/System/Applications/App Store.app",
      "/Applications/AudioGridderPluginTray.app",
      "/Applications/Autodesk",
      "/System/Applications/Automator.app",
      "/Applications/BetterTouchTool.app",
      "/Applications/BL Group Craft.app",
      "/Applications/Blender.app",
      "/Applications/BLGroupcraftEN.app",
      "/System/Applications/Books.app",
      "/System/Applications/Calculator.app",
      "/System/Applications/Calendar.app",
      "/Applications/ChatGPT.app",
      "/Applications/ChatGPT Atlas.app",
      "/System/Applications/Chess.app",
      "/Applications/Chrome Remote Desktop Host Uninstaller.app",
      "/Applications/Cinema",
      "/Applications/Claude.app",
      "/System/Applications/Clock.app",
      "/System/Applications/Contacts.app",
      "/Applications/Cursor.app",
      "/Applications/DecentSampler.app",
      "/System/Applications/Dictionary.app",
      "/Applications/Discord.app",
      "/System/Applications/FaceTime.app",
      "/Applications/Family Tree Builder.app",
      "/System/Applications/FindMy.app",
      "/System/Applications/Font Book.app",
      "/System/Applications/Freeform.app",
      "/Applications/Games",
      "/Applications/Gephi.app",
      "/Applications/GIMP.app",
      "/Applications/Glyphs 3.app",
      "/Applications/Google Chrome.app",
      "/Applications/Google Docs.app",
      "/Applications/Google Drive.app",
      "/Applications/Google Sheets.app",
      "/Applications/Google Slides.app",
      "/Applications/gpt4all",
      "/Applications/GPT4All.app",
      "/Applications/Hadron",
      "/System/Applications/Home.app",
      "/System/Applications/Image Capture.app",
      "/Applications/Inkscape.app",
      "/System/Applications/iPhone Mirroring.app",
      "/Applications/iZotope RX 11 Audio Editor.app",
      "/Applications/JustStream.app",
      "/Applications/Karabiner-Elements.app",
      "/Applications/Karabiner-EventViewer.app",
      "/Applications/KeyFinder.app",
      "/Applications/LangGraph Studio.app",
      "/System/Applications/Launchpad.app",
      "/Applications/LibreOffice.app",
      "/Applications/LICEcap.app",
      "/Applications/LM Studio.app",
      "/System/Applications/Mail.app",
      "/System/Applications/Maps.app",
      "/Applications/MeldaProduction",
      "/System/Applications/Messages.app",
      "/Applications/Microsoft Excel.app",
      "/Applications/Microsoft PowerPoint.app",
      "/Applications/Microsoft Remote Desktop.app",
      "/Applications/Microsoft Word.app",
      "/Applications/Miro.app",
      "/System/Applications/Mission Control.app",
      "/Applications/Music",
      "/System/Applications/Music.app",
      "/System/Applications/News.app",
      "/System/Applications/Notes.app",
      "/Applications/Notion.app",
      "/Applications/OBS.app",
      "/Applications/Obsidian.app",
      "/Applications/Ollama.app",
      "/Applications/Omnisphere.app",
      "/Applications/OneDrive.app",
      "/Applications/Opera.app",
      "/Applications/Parallels Desktop.app",
      "/System/Applications/Passwords.app",
      "/System/Applications/Photo Booth.app",
      "/System/Applications/Photos.app",
      "/Applications/Pinokio.app",
      "/System/Applications/Podcasts.app",
      "/System/Applications/Preview.app",
      "/Applications/Psiphon.app",
      "/Applications/Python 3.12",
      "/Applications/qbittorrent.app",
      "/System/Applications/QuickTime Player.app",
      "/Applications/REAPER.app",
      "/System/Applications/Reminders.app",
      "/Applications/Safari.app",
      "/Applications/SF Symbols beta.app",
      "/Applications/ShareMouse.app",
      "/System/Applications/Shortcuts.app",
      "/Applications/Shutter Encoder.app",
      "/System/Applications/Siri.app",
      "/Applications/SketchUp 2023",
      "/Applications/Soda Player.app",
      "/Applications/Soft",
      "/Applications/spoof-dpi ",
      "/Applications/StarUML.app",
      "/Applications/Steam.app",
      "/System/Applications/Stickies.app",
      "/System/Applications/Stocks.app",
      "/Applications/Swar Dashboard.app",
      "/System/Applications/System Settings.app",
      "/Applications/Tailscale.app",
      "/Applications/Tailscale.localized",
      "/Applications/Telegram.app",
      "/System/Applications/TextEdit.app",
      "/Applications/TextSniper.app",
      "/System/Applications/Time Machine.app",
      "/System/Applications/Tips.app",
      "/Applications/Tools",
      "/System/Applications/TV.app",
      "/Applications/Utilities",
      "/Applications/VLC.app",
      "/System/Applications/VoiceMemos.app",
      "/Applications/Voicemod.app",
      "/Applications/Wacom Tablet.localized",
      "/Applications/Waves",
      "/System/Applications/Weather.app",
      "/Applications/Wolow.app",
      "/Applications/Work",
      "/Applications/Yandex.app",
      "/Applications/Yandex.Disk.2.app",
      "/Applications/Yandex.Telemost.app",
      "/Applications/yEd.app",
      "/Applications/Youka.app",
      "/Applications/Zrythm.app"
    ]
  },
  "mcp_time_snapshot": {
    "timestamp": "2025-12-01T02:36:59.997443+00:00",
    "provider": "demo-snapshot-time"
  },
  "current_datetime": "2025-12-01T05:37:06.579024"
}

#### User Request
КАкие из этих программ для музыки?

---
# Tools
### web_search

#### Description

Performs a web search for a given query, fetches content from the top results,
and returns a formatted string with the findings. This is useful for getting
up-to-date information or researching topics.

#### Arguments

required: query

##### query

- title: Query
- type: string

The search query to find information on the web.


---

### run_ui_scenario

#### Description

Executes a complex UI interaction scenario based on a natural language task (e.g., 'log in to twitter').
This is a powerful but slow and expensive tool. Use simpler tools if possible.
It gives an underlying AI agent full control over the mouse and keyboard to achieve the task.
Its settings are configured in the 'Vision' > 'Screenshot View Agent' section of the main app settings.

#### Arguments

required: task

##### task

- title: Task
- type: string

A natural language description of the UI task to perform (e.g., 'log in to twitter', 'find the most recent email from bob').


---

### screenshot_view

#### Description

Reads the latest screenshot from the disk, encodes it to base64, and returns it.
This allows the agent to "look" at the screen. The screenshot is taken automatically
before the agent is invoked.


---

### openai-gpt-image-mcp_create-image

#### Arguments

required: prompt, background, model, moderation, n, output_compression, output_format, quality, size, user, output, file_output

##### prompt

- title: Prompt
- type: string
##### background

- title: Background
- type: string
##### model

- title: Model
- type: string
##### moderation

- title: Moderation
- type: string
##### n

- title: N
- type: integer
##### output_compression

- title: Output Compression
- type: integer
##### output_format

- title: Output Format
- type: string
##### quality

- title: Quality
- type: string
##### size

- title: Size
- type: string
##### user

- title: User
- type: string
##### output

- title: Output
- type: string
##### file_output

- title: File Output
- type: string

Absolute path to save the image file, including the desired file extension (e.g., /path/to/image.png). If multiple images are generated (n > 1), an index will be appended (e.g., /path/to/image_1.png).


---

### openai-gpt-image-mcp_edit-image

#### Arguments

required: image, prompt, mask, model, n, quality, size, user, output, file_output

##### image

- title: Image
- type: string

Absolute image path or base64 string to edit.

##### prompt

- title: Prompt
- type: string

A text description of the desired edit. Max 32000 chars.

##### mask

- title: Mask
- type: string

Optional absolute path or base64 string for a mask image (png < 4MB, same dimensions as the first image). Fully transparent areas indicate where to edit.

##### model

- title: Model
- type: string
##### n

- title: N
- type: integer

Number of images to generate (1-10).

##### quality

- title: Quality
- type: string

Quality (high, medium, low) - only for gpt-image-1.

##### size

- title: Size
- type: string

Size of the generated images.

##### user

- title: User
- type: string

Optional user identifier for OpenAI monitoring.

##### output

- title: Output
- type: string

Output format: base64 or file path.

##### file_output

- title: File Output
- type: string

Absolute path to save the output image file, including the desired file extension (e.g., /path/to/image.png). If n > 1, an index is appended.


---

### PythonCodeExecutor

#### Description

Executes Python code to control the computer. The `computer` object is pre-defined and provides access to system utilities. Do not `import computer`.

**Available utilities:**

- computer.browser:
	- .**go_to_url**(url: string) — Opens a URL in the default web browser using native OS commands.
	- .**search_google**(query: string) — Searches Google for the given query and opens the results in the browser.
	- .**search_youtube**(query: string) — Searches YouTube for the given query and opens the results in the browser.
- computer.calendar:
	- .**create_calendar_event**(title: string, start_time: string, end_time: string, calendar_name: any) — Creates a new calendar event. Start and end times should be in "YYYY-MM-DD HH:MM:SS" format. If calendar_name is not provided, the first available calendar will be used.
	- .**get_calendar_events**(start_date: string, end_date: any) — Fetches calendar events for a given date or date range. Dates should be in YYYY-MM-DD format. If end_date is not provided, it defaults to the start_date.
- computer.clipboard:
	- .**copy_selection_to_clipboard**() — Simulates a 'copy' command (e.g., Command+C or Ctrl+C) to copy whatever is currently selected into the clipboard.
	- .**get_clipboard_content**() — Returns the current text content of the system clipboard.
	- .**paste_from_clipboard**() — Simulates a 'paste' command (e.g., Command+V or Ctrl+V) to paste the clipboard content at the current cursor position.
	- .**set_clipboard_content**(text: string) — Sets the system clipboard to the specified text.
- computer.files:
	- .**edit_file**(path: string, original_text: string, replacement_text: string) — Edits a file on the filesystem, replacing a snippet of original text with replacement text. It's useful for small, precise changes.
	- .**search_files**(query: string, in_dir: any, content_match: boolean) — Search the filesystem for files or directories matching the given query.
- computer.mail:
	- .**get_emails**(number: integer, unread: boolean) — Retrieves a specified number of emails from the inbox of the Mail app, optionally filtering for only unread emails. Capped at 50 emails.
	- .**mark_email_as_read**(message_id: string) — Marks a specific email as read using its message ID. You should get the message_id from the `get_emails` function first.
	- .**send_email**(to: string, subject: string, body: string) — Sends an email with the given parameters using the default Mail app. 'to' should be a comma-separated list of recipient email addresses.
- computer.terminal:
	- .**execute_terminal_command**(command: string) — Executes a shell command and returns its output. Use it for simple, non-interactive commands.
- computer.demo-time:
	- .**add**(a: integer, b: integer) — Adds two numbers.
	- .**now**(iso: boolean) — Returns the current time. iso=True -> ISO 8601.

#### Arguments

required: code

##### code

- title: Code
- type: string

The Python code to execute using the 'computer' object.


---

### recall_memory

#### Description

Use this tool to recall information from your long-term memory about the user's recent activity.
You can call multiple memory functions at once to gather comprehensive context.
Provide a JSON list of function calls in the 'actions' parameter.

**Tip for multi-step search:** If you need to find a full conversation or activity log around a specific topic, first perform a broad search using a keyword. The results will include timestamps. Then, perform a second, more precise search using the `start_time` and `end_time` parameters based on those timestamps to retrieve the full context.

**Available functions:**

- .**conversation.search_conversation**(text: string, start_time: string, end_time: string, limit: integer)
Searches the conversation history. Can filter by text, a time range, or both.
The maximum time period that can be searched is 14 days. For longer periods, make multiple requests.

:param text: The text to search for in the conversation. Optional.
:param start_time: The start of the time period to search, in ISO 8601 format (e.g., '2023-10-27T10:00:00Z'). Optional.
:param end_time: The end of the time period to search, in ISO 8601 format. If not provided, defaults to now. Optional.
:param limit: The maximum number of matching messages to return.
:return: A formatted string of matching messages, or a message indicating no matches were found.

- .**user_activity.search_activity**(text: string, start_time: string, end_time: string, watchers: array)
Searches the user's activity history across different watchers (e.g., window, filesystem).
Can filter by text, a time range, a list of specific watchers, or any combination.
The maximum time period that can be searched is 7 days. For longer periods, make multiple requests.

:param text: The text to search for in the activity data. Optional.
:param start_time: The start of the time period to search, in ISO 8601 format (e.g., '2023-10-27T10:00:00Z'). Optional.
:param end_time: The end of the time period to search, in ISO 8601 format. If not provided, defaults to now. Optional.
:param watchers: A list of watcher names to search in. Currently enabled watchers: ['afk', 'filesystem', 'window']. If not provided, searches all available watchers. Optional.
:return: A formatted string summarizing the findings.

#### Arguments

required: actions

##### actions

- title: Actions
- type: string

A JSON-formatted list of function calls to retrieve memory. E.g., `[{{"function": "user_activity.search_activity", "args": {{"text": "my_document.txt"}}}}]`


---
