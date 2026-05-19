# Project Legend: Smart Publish

## 1. Context & Client Background
**Client:** A large Eastern European digital marketing and media holding (under strict NDA). 
**Timeline:** 2024 – 2025.
**The Problem:** The client managed content operations for over 20+ enterprise brands and internal media outlets. Their editorial teams were wasting hundreds of hours manually rewriting drafts, adapting them for different platforms (corporate sites, LinkedIn, X, Telegram), resizing media, and publishing through legacy CMS platforms and social APIs.

## 2. Product Overview
**Project Name:** Smart Publish / AI Publishing Automation Platform
**Concept:** An agentic workflow platform that acts as a centralized content hub. It ingests rough drafts or raw notes, uses an LLM pipeline to generate channel-specific versions (respecting character limits, tone of voice, and formatting), and orchestrates multi-channel publishing after mandatory human review.

## 3. My Role: Lead AI Engineer / AI Architect
I led the engineering of the AI pipeline and backend architecture. My responsibilities included:
*   Designing the system architecture, moving away from a simple "chatbot wrapper" to a predictable, multi-step Agentic Workflow.
*   Developing the core AI pipeline: Draft ingestion -> Fact extraction -> Content generation -> Channel-specific adaptation.
*   Designing the "Custom Website Connector" – a flexible mapping system to push content into legacy corporate CMSs via REST APIs without hardcoding each integration.
*   Implementing a mandatory "Human-in-the-Loop" (HITL) approval system to guarantee brand safety and prevent LLM hallucinations from going live.

## 4. Tech Stack & Architecture
*   **Backend:** Python, FastAPI.
*   **AI/LLM Layer:** OpenAI API / Claude, LangChain-style orchestration for prompt chaining.
*   **Workflow & Automation:** n8n / Celery (background job processing, retries, and rate-limit handling).
*   **Database:** PostgreSQL (for drafts, approval states, and connector configs), S3 for media storage.
*   **Integrations:** Direct social media APIs (LinkedIn, X, Telegram), Webhooks, and custom REST API endpoints for internal CMSs.

## 5. Key Engineering Challenges Solved (Interview Talking Points)
*   **Predictability over Autonomy:** Business stakeholders were afraid of AI publishing unverified content. I solved this by decoupling generation from publication. The AI acts as a drafter; the state machine requires explicit human approval before the n8n/background worker triggers the publishing API.
*   **Handling API Rate Limits:** Social APIs (especially LinkedIn and X) have strict rate limits. I designed a robust queuing system with exponential backoff and retry mechanisms to ensure high-volume publishing didn't result in blocked accounts.
*   **Dynamic Prompting & Tone of Voice:** Implemented a system where each channel connector injected its own system prompt and constraints (e.g., "Max 280 chars, use 2 hashtags" for X, vs. "Professional corporate tone, long-form" for LinkedIn), ensuring context was preserved across adaptations.
*   **Context Management (No-RAG approach):** For highly specific brand guidelines, instead of a lossy RAG implementation, I engineered a full-context injection approach, feeding entire editorial guideline documents into the prompt window to maintain absolute consistency in output style.

## 6. Business Impact
*   Reduced time-to-publish across multi-channel campaigns by approx. 70%.
*   Eliminated the need for manual copy-pasting and formatting across 5+ different platforms per article.
*   Provided a unified, brand-safe workspace for editors to manage AI-generated content.
