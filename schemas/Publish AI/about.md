# Smart Publish

## Product Idea

Smart Publish is a content operations platform for creating, adapting, scheduling, and publishing news posts from a single workspace. It can work both as a B2B tool for editorial teams and businesses, and as a B2C/productivity tool for individual creators, small website owners, and independent publishers.

The core idea is simple: an editor or business user writes a rough news draft, attaches photos or videos, selects publishing destinations, reviews AI-generated versions, and publishes the content to websites and social platforms. The platform reduces repetitive editorial work while keeping the workflow predictable and human-controlled.

The system was designed not as a generic chatbot, but as a structured publishing tool with an AI layer inside it: draft intake, content generation, review, scheduling, publishing, and connector management.

## Business Problem

Small media teams, company websites, marketing departments, independent creators, and small business owners often publish the same information across several channels:

- personal website, corporate website, or news portal;
- Telegram or messenger channels;
- Facebook, X/Twitter, LinkedIn, Reddit, and other social platforms;
- custom websites with their own CMS or API;
- internal announcements, partner channels, or personal brand channels.

The manual workflow is repetitive: rewrite the same draft for every platform, resize or attach media, prepare metadata, copy text into each admin panel, check formatting, schedule publication, and track what was already posted.

The platform solves this by turning one draft into several channel-specific publication packages and sending them to connected destinations through predefined or custom connectors. For a company, this reduces editorial and marketing operations work. For an individual user, it acts as a personal publishing assistant that helps maintain a consistent presence across a website and social platforms.

## Main User Workflow

1. A user creates a draft in the web application or sends it through Telegram.
2. The draft may include text, notes, photos, videos, links, and attachments.
3. The user selects one or more publishing destinations.
4. The AI pipeline extracts the main facts and detects missing information.
5. The system generates platform-specific versions using templates and system prompts.
6. The user reviews the generated content, edits it if needed, and approves publication.
7. The platform either publishes immediately or schedules the post for later.
8. The system stores the generated versions, publication status, logs, and errors.

The important product principle is that the AI does not publish blindly. The workflow is predictable: generate, preview, approve, publish.

## Publishing Destinations

The platform supports two classes of publishing destinations.

### Built-in Social Connectors

These connectors cover common social and content platforms:

- Facebook;
- X/Twitter;
- LinkedIn;
- Reddit;
- Telegram;
- other modern social platforms through their APIs or automation wrappers.

Each destination can have its own formatting rules, text length limits, tone, hashtags, media handling, and prompt template.

### Custom Website Connector

The custom connector is the more flexible part of the system. It allows a client or individual user to connect a website or CMS that does not have a built-in integration.

The user or admin can configure:

- base API URL;
- authorization method;
- headers and tokens;
- required API requests;
- request body mapping;
- media upload endpoint;
- article creation endpoint;
- publication status rules;
- response parsing rules.

This makes it possible to connect a custom website API without hardcoding every integration into the core system.

## AI Content Pipeline

The AI layer is intentionally structured as a pipeline rather than a free-form chat flow.

### Draft Understanding

The first step analyzes the incoming draft:

- detects the topic and intended publication type;
- extracts facts, names, dates, links, and entities;
- separates source notes from publishable text;
- identifies missing fields or unclear parts;
- prepares a normalized internal representation of the draft.

### Article Generation

The second step creates the main news article:

- headline;
- lead paragraph;
- body;
- summary;
- metadata;
- tags;
- SEO-oriented fields where needed.

The output is generated according to the selected editorial style and publication template.

### Channel Adaptation

The third step adapts the same source material to different destinations:

- full website article;
- short Telegram announcement;
- LinkedIn post;
- X/Twitter thread or short post;
- Reddit-style post;
- Facebook post;
- custom CMS payload.

Each channel can have its own system prompt, formatting template, constraints, and media rules.

### Review and Approval

The generated content is shown to the user before publication. The user can:

- edit the generated text;
- regenerate a specific version;
- change tone or length;
- approve only selected channels;
- schedule publication;
- publish immediately.

## Assistant Layer

In addition to the deterministic publishing pipeline, the platform includes an assistant layer.

The assistant helps the user:

- create posts from scratch;
- improve a draft;
- ask for promotion ideas;
- choose publication channels;
- adapt tone for a specific audience;
- prepare a publishing plan;
- reuse previous notes and knowledge base materials.

This assistant is not the main publishing mechanism. It sits above the workflow and helps the user think, plan, and prepare content before the structured pipeline runs.

## Knowledge Base

The platform can store notes, files, and reference materials that the AI uses as context.

Examples:

- company or personal brand descriptions;
- product facts;
- editorial guidelines;
- previous posts;
- campaign notes;
- client-specific or creator-specific terminology;
- frequently used links and media references.

This knowledge base allows generated posts to be more consistent with the client's style and domain context.

## MCP and External Context

Later, the platform was extended with MCP-style tool integration so the assistant could use additional external context.

Potential MCP/tool use cases:

- read extra files or notes;
- fetch information from connected systems;
- call internal APIs;
- search external knowledge sources;
- enrich a draft before generation;
- validate generated content against custom rules.

This made the assistant layer more extensible without turning the core publishing pipeline into a collection of hardcoded integrations.

## Scheduling

The platform supports publication planning:

- immediate publication;
- scheduled publication;
- draft-only mode;
- per-channel approval;
- retry after failed publication;
- publication status tracking.

Scheduling is important because one source draft may need to be published across multiple destinations at different times.

## Architecture Overview

The system can be described as several connected modules.

### Application Layer

- Web application for creating drafts, reviewing generated versions, managing channels, and scheduling posts.
- Telegram bot for quick draft submission and lightweight interaction.
- Admin area for connector configuration and publication status.

### Workflow Core

- FastAPI backend for API endpoints and business logic.
- Background jobs or n8n workflows for processing drafts and publication tasks.
- Task status tracking for retries, errors, and scheduled runs.

### AI Layer

- LLM-based draft understanding.
- Prompt/template system for each publishing destination.
- Content generation and channel adaptation.
- Assistant mode for brainstorming and promotion advice.
- Knowledge base retrieval for contextual generation.

### Connector Layer

- Built-in connectors for common social platforms.
- Telegram integration.
- CMS integration through REST APIs.
- Custom website connector with configurable authorization and request mapping.

### Data Layer

- Draft storage.
- Generated versions.
- Media files.
- Knowledge base documents and notes.
- Publication logs.
- Connector configuration.

## Stack

The exact implementation can vary by deployment, but the project was built around the following stack and integration approach:

- **Backend:** Python, FastAPI.
- **Workflow automation:** n8n, background jobs.
- **AI:** OpenAI API, LangChain-style prompt orchestration, structured prompts.
- **Integrations:** Telegram API, REST APIs, CMS APIs, social platform APIs.
- **Data:** relational database for drafts, versions, configs, and publication states; file/object storage for media.
- **Knowledge base:** vector search/RAG-style context for notes and reference documents.
- **Extensibility:** MCP-style tools for external context and custom integrations.
- **Operations:** logs, task statuses, retries, publication audit trail.

## My Role

I worked as Lead AI Engineer on the project.

My responsibilities included:

- shaping the product concept and AI workflow;
- designing the system architecture;
- building the backend and publishing pipeline;
- designing the LLM prompt structure for news generation and channel adaptation;
- integrating Telegram and CMS APIs;
- designing the custom connector approach;
- preparing the system for additional publishing destinations;
- adding the assistant/knowledge-base direction for richer content generation.

## Why This Project Matters

The project was important because it moved beyond a simple "generate a post" demo. It explored a more practical AI product pattern:

- AI is embedded into a real business workflow;
- users keep control through review and approval;
- publishing is handled through integrations, not copy-paste;
- every channel has its own rules and prompts;
- custom APIs can be connected without rewriting the product;
- the assistant layer supports planning, while the pipeline handles execution.

This is the same product logic that later became central to my AI work: not just chat, but AI systems that operate inside real workflows and connect to external tools.
