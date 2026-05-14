# AI Publishing Automation Platform

An AI-powered publishing workflow that turns raw news drafts into publication-ready content for a website and social media channels.

### Goal

The client needed a way to reduce manual editorial work and publish content faster. Drafts could arrive in different formats and through different channels, while the final result had to be structured, edited, formatted, and published through the client's CMS.

### What I Built

- Designed a multi-channel ingestion flow for incoming drafts, including email and Telegram.
- Built an LLM processing pipeline that analyzed the draft, cleaned up the structure, rewrote text into a news format, and prepared metadata.
- Integrated the workflow with a CMS API for automatic publishing.
- Added support for adapting the same content for social media distribution.
- Implemented configurable prompts and processing steps so the workflow could be adjusted for different editorial styles.
- Prepared the architecture so additional channels and publishing destinations could be connected later.

### Stack

Python, FastAPI, OpenAI API, Telegram API, REST APIs, CMS integration, n8n, prompt engineering, workflow automation.

### My Role

Lead AI Engineer. I was responsible for discovery, architecture, backend implementation, AI workflow design, integrations, and delivery of the working prototype/product.
