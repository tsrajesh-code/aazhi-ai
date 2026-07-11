# 6. Technology Stack

## Recommended Stack

| Layer | Technology | Recommendation |
|---|---|---|
| Desktop shell | Electron | Best fit for cross-platform desktop, native integration, mature packaging. |
| UI framework | React | Mature ecosystem, strong component patterns, excellent desktop app compatibility. |
| Language | TypeScript | Required for maintainability, plugin SDK contracts, and frontend correctness. |
| Styling | Tailwind CSS | Fast design iteration, consistent tokens, strong utility model. |
| Backend API | FastAPI | Excellent Python AI ecosystem integration, OpenAPI support, async capabilities. |
| Backend language | Python | Best ecosystem for AI, embeddings, model tooling, image, voice, and data processing. |
| Relational database | PostgreSQL | Production-grade relational store for cloud and enterprise services. |
| Local relational store | SQLite | Recommended for purely local single-user offline data. |
| Vector database | ChromaDB | Good local-first vector store for MVP and desktop usage. |
| Local models | Ollama | Practical local model manager and runtime for desktop users. |
| Cloud models | OpenAI-compatible provider adapters | Keep provider layer flexible and avoid hard coupling. |
| State management | TanStack Query + Zustand | Clear split between server state and local UI state. |
| Testing | Vitest, Playwright, Pytest | Covers frontend units, desktop flows, backend services. |
| Logging | structlog / loguru + Electron logs | Structured logs across Python and desktop layers. |
| Monitoring | OpenTelemetry-ready design | Enables future local diagnostics and cloud observability. |
| Packaging | electron-builder or Electron Forge | Mature installer generation and signing workflows. |
| Auto update | electron-updater | Common update flow with signed release artifacts. |

## Technology Rationale

| Decision | Why |
|---|---|
| Electron over native-only frameworks | Faster cross-platform delivery, web UI ecosystem, plugin and tool integrations. |
| FastAPI over Node backend | Python AI ecosystem is stronger for local models, embeddings, images, audio, and ML workflows. |
| TypeScript everywhere possible | Reduces runtime errors across UI, plugin SDK, and generated API clients. |
| PostgreSQL plus SQLite | PostgreSQL supports cloud/team scale; SQLite gives robust local-first desktop mode. |
| ChromaDB first | Good MVP vector store; can later abstract to pgvector, Qdrant, Milvus, or managed vector services. |
| Ollama first | User-friendly local model management with broad model availability. |

## Model Provider Strategy

| Provider Type | Examples | Use |
|---|---|---|
| Local LLM | Ollama models | Offline/private chat, coding, summarization. |
| Cloud LLM | OpenAI-compatible APIs | High-quality reasoning, coding, tool use. |
| Embeddings | Local or cloud embeddings | Memory, semantic search, project indexing. |
| Image generation | Local diffusion or cloud APIs | Image studio, visual assets. |
| Speech-to-text | Whisper/local or cloud STT | Voice input. |
| Text-to-speech | Local TTS or cloud voices | Voice output. |

## Testing Framework

| Test Type | Tool | Scope |
|---|---|---|
| Frontend unit | Vitest | Components, hooks, utilities. |
| Frontend integration | React Testing Library | UI behavior and state. |
| End-to-end | Playwright | App flows, chat streaming, settings, plugins. |
| Backend unit | Pytest | Services, repositories, model adapters. |
| Backend integration | Pytest + test database | API, database, vector store, workers. |
| Security tests | Semgrep, Bandit, npm audit, pip-audit | Static and dependency checks. |
| Performance tests | Locust or custom harness | Streaming latency, indexing, search, model routing. |
| AI regression tests | Prompt/model eval harness | Quality, refusal, retrieval, tool behavior. |

## Logging and Monitoring

| Area | Recommendation |
|---|---|
| Local logs | Store structured logs with rotation and user export controls. |
| Audit logs | Separate security/audit event stream from debug logs. |
| Crash reporting | Optional and explicit user consent. |
| Telemetry | Off by default or privacy-forward; never include prompts without explicit opt-in. |
| Tracing | Use OpenTelemetry-compatible internal spans for future cloud diagnostics. |

## Packaging and Auto Update

| Platform | Packaging |
|---|---|
| Windows | Signed NSIS or MSI installer. |
| macOS | Signed and notarized DMG/PKG. |
| Linux | AppImage first; deb/rpm later. |

Auto-update should require signed release artifacts and staged rollout support.

