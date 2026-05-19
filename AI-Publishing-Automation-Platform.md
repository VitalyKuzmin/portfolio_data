# Smart Publish

An AI-assisted publishing platform developed for preparing, adapting, scheduling, and publishing news content across websites and social platforms.

The project was not a fully autonomous agent. It was closer to a structured AI assistant with predictable publishing pipelines: the user creates or uploads a draft, the AI prepares versions for selected destinations, the user reviews the result, and the system publishes or schedules the content.

## Product Idea

Smart Publish gives a user one workspace for content operations:

- create a news draft manually;
- send a draft through Telegram;
- attach photos, videos, documents, or notes;
- use AI to transform the draft into a publication-ready article;
- adapt the same content for different platforms;
- review and approve generated versions;
- publish immediately or schedule a content plan for later.

The product can be used by editorial teams, marketing teams, small businesses, or individual creators who need to maintain a website and several social channels without manually rewriting the same content many times.

## Main Workflow

1. A user creates a draft in the app or sends it through Telegram.
2. The user attaches media, notes, documents, or reference materials.
3. The system extracts the key facts and prepares a normalized draft.
4. AI templates generate a website article and platform-specific versions.
5. The user reviews, edits, regenerates, or approves the content.
6. The platform publishes to connected websites and social channels.
7. The user can schedule single posts or a series of publications in advance.

This made the product useful even with a relatively linear AI architecture: the value was in connecting content generation with real publishing workflows.

## AI Pipeline

The AI part was based on predictable steps rather than open-ended autonomy:

- **Draft understanding:** extract facts, topic, source notes, links, and missing information.
- **Article generation:** create headline, lead, body, summary, tags, and metadata.
- **Channel adaptation:** rewrite the same content for Telegram, LinkedIn, X/Twitter, Reddit, Facebook, or custom CMS formats.
- **Style templates:** use system prompts and templates per platform, tone, and publication type.
- **Review loop:** keep a human approval step before publishing.

There was also an assistant layer above the pipeline. The user could ask for promotion ideas, improve a draft, create a post from scratch, or plan a month of publications.

## Publishing Integrations

Smart Publish supported both predefined and custom destinations.

Built-in connector ideas included:

- Telegram;
- Facebook;
- X/Twitter;
- LinkedIn;
- Reddit;
- website CMS APIs.

The custom website connector was the more flexible part. An admin could configure:

- API base URL;
- authorization method;
- headers and tokens;
- media upload endpoint;
- article creation endpoint;
- request body mapping;
- response parsing and publication status rules.

This allowed the platform to publish to client-specific websites without hardcoding every CMS integration into the core product.

## Knowledge Base and Context

The platform also supported storing notes, files, and reference materials that could be used by the AI when generating content.

Examples:

- editorial guidelines;
- company or personal brand descriptions;
- product facts;
- previous posts;
- campaign notes;
- terminology and reusable links.

Later, the assistant direction was extended with MCP-style tool access so additional external context could be connected without rebuilding the whole pipeline.

## Stack

- **Backend:** Python, FastAPI.
- **Workflow automation:** n8n, background jobs.
- **AI:** OpenAI API, LangChain-style prompt orchestration, structured prompts.
- **Integrations:** Telegram API, REST APIs, CMS APIs, social platform APIs.
- **Data:** relational database for drafts, generated versions, connector configs, publication states, and logs.
- **Extensibility:** configurable connectors, prompt templates, MCP-style external context.

## My Role

I worked as Lead AI Engineer. I designed the product architecture, built the backend and AI workflow, created the prompt/template structure, integrated Telegram and CMS APIs, designed the custom connector approach, and prepared the system for additional publishing destinations.
