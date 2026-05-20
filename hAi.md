# hAi

A local-first desktop AI assistant for computer context, personal memory, voice interaction, local models, and tool use.

hAi is my personal R&D project with a public/open-source release planned. I started it to explore what a real personal AI assistant could become: not just a chat window, but a system that understands the user's computer context, works with local and cloud models, uses tools, and gradually becomes a universal desktop companion.

### Goal

The goal is to build a practical assistant platform that can run locally, use personal context safely, interact with desktop workflows, support voice, connect external tools through MCP, and serve as my real environment for AI assistant research.

### Architecture Overview

![hAi concept overview](img/5.jpg)

**Local assistant layer:** desktop app, Python/FastAPI backend, local memory, ActivityWatch context, screenshots, SQLite/LanceDB storage, LiveKit voice services, MCP tools, script execution, local/cloud LLM routing, and AI-assisted development workflows.

### What I Built

- Designed the architecture of a distributed local desktop assistant.
- Built the backend core for agent logic, memory, model routing, and tool use.
- Integrated local and cloud LLMs, including Ollama-based local model workflows.
- Added ActivityWatch-based computer activity context and snapshot/screenshot-oriented context experiments.
- Built memory and storage concepts with SQLite and LanceDB.
- Integrated voice-related components through LiveKit and STT/TTS tools.
- Added MCP support for connecting local tools, files, and external systems.
- Use the project daily as an R&D environment for local models, Mac Studio inference optimization, agent UX, and AI-assisted development.

### Stack

Python, FastAPI, Electron, React, TypeScript, LangChain, SQLAlchemy, SQLite, LanceDB, ActivityWatch, LiveKit, MCP, Ollama, OpenAI, Gemini, Whisper, Piper, Moondream.

### My Role

Solo founder and lead developer. I designed and built the system end-to-end: architecture, backend core, agent logic, memory concepts, local/cloud model integrations, tool use, and desktop context experiments.

I continue to use hAi as my personal AI assistant R&D environment while preparing the project for public/open-source release.
