# 3. Software Requirements Specification

## Scope

AAZHI AI is a cross-platform desktop application supporting AI chat, coding assistance, memory, local AI models, image generation/editing, voice, agents, productivity tools, and plugins.

## Functional Requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-001 | Users can create, rename, archive, search, and delete chat conversations. | Must |
| FR-002 | Users can send prompts to local and cloud AI models. | Must |
| FR-003 | Users can choose default models per task type: chat, code, image, embedding, voice. | Must |
| FR-004 | Users can create project workspaces with files, conversations, settings, and memories. | Must |
| FR-005 | The app can index selected project files for semantic search with user approval. | Must |
| FR-006 | The app can generate and retrieve conversation, project, and user memories. | Must |
| FR-007 | Users can view, edit, disable, export, and delete memories. | Must |
| FR-008 | Users can connect local models through Ollama. | Must |
| FR-009 | Users can configure cloud model API keys securely. | Must |
| FR-010 | Users can use coding assistance for explanation, generation, debugging, tests, and review. | Must |
| FR-011 | Users can browse project files inside the app. | Must |
| FR-012 | Users can generate images from text prompts. | Should |
| FR-013 | Users can edit images using prompts, masks, or reference images. | Should |
| FR-014 | Users can use voice input and receive spoken responses. | Should |
| FR-015 | Users can install, enable, disable, configure, and remove plugins. | Should |
| FR-016 | Plugins must declare permissions before use. | Must |
| FR-017 | Agents can execute multi-step tasks only within approved scopes. | Should |
| FR-018 | Users can approve or deny sensitive actions such as file writes, terminal commands, network access, and plugin calls. | Must |
| FR-019 | The app logs important actions for audit and debugging. | Must |
| FR-020 | The app supports offline usage for local chat, local memory, local search, and local project workflows. | Must |

## Non-Functional Requirements

| Category | Requirement |
|---|---|
| Reliability | The app should recover gracefully from model failures, network failures, and plugin crashes. |
| Availability | Local-first functions should remain available without internet access. |
| Usability | Primary workflows should require minimal configuration for non-technical users. |
| Extensibility | New model providers, tools, plugins, and memory stores should be added through interfaces. |
| Observability | Logs, metrics, traces, and audit events should be structured and searchable. |
| Portability | The app should support Windows, macOS, and Linux with shared core logic. |
| Privacy | User data should be local by default unless cloud sync is explicitly enabled. |
| Compliance Readiness | Architecture should support future SOC 2, GDPR, HIPAA-adjacent, and enterprise audit needs. |

## Performance Requirements

| ID | Requirement | Target |
|---|---|---|
| PERF-001 | App cold start on typical hardware | Under 5 seconds after first launch |
| PERF-002 | Chat UI response to user input | Under 100 ms perceived latency |
| PERF-003 | First token from local model | Depends on model, show progress within 500 ms |
| PERF-004 | Semantic search over 10k chunks | Under 1 second for common queries |
| PERF-005 | Conversation list loading | Under 500 ms for 10k conversations with pagination |
| PERF-006 | Memory retrieval | Under 300 ms for common context assembly |
| PERF-007 | Plugin activation | Under 2 seconds for normal plugins |
| PERF-008 | Image generation progress | Show queued/running state within 500 ms |

## Security Requirements

| ID | Requirement |
|---|---|
| SEC-001 | Secrets must be encrypted at rest using OS keychain or platform secure storage. |
| SEC-002 | Plugins must run in a sandbox with declared permissions. |
| SEC-003 | Agent actions must be auditable and approval-gated by risk level. |
| SEC-004 | File access must be scoped to user-selected workspaces or explicit grants. |
| SEC-005 | Network calls must be visible by provider/plugin and configurable by policy. |
| SEC-006 | User memory must be inspectable and deletable. |
| SEC-007 | Sensitive prompts should support redaction before cloud model submission. |
| SEC-008 | Updates must be signed and verified. |

## Scalability Requirements

| Layer | Requirement |
|---|---|
| Desktop app | Support large local histories and many workspaces without UI degradation. |
| Local services | Modular services should scale by moving heavy tasks into workers. |
| Cloud services | Optional sync, collaboration, and marketplace services should scale horizontally. |
| Data model | Schema should support multi-user, multi-workspace, organization, and enterprise modes. |
| Plugin ecosystem | Plugin registry and permission model should support third-party growth. |

## Maintainability Requirements

| Requirement | Approach |
|---|---|
| Clear boundaries | Use package boundaries for UI, core, AI, memory, plugins, storage, and security. |
| Typed contracts | TypeScript interfaces and OpenAPI schemas for cross-layer contracts. |
| Testability | Unit, integration, end-to-end, security, and model behavior tests. |
| Migration safety | Versioned database migrations and plugin API versions. |
| Documentation | Architecture decisions, API contracts, contribution guide, and release guide. |

## Offline Support

| Capability | Offline Behavior |
|---|---|
| Chat | Works with installed local models. |
| Memory | Local memory retrieval and editing remain available. |
| Project search | Previously indexed files remain searchable. |
| Image generation | Works if local image models are installed. |
| Voice | Works with local speech-to-text and text-to-speech models when installed. |
| Plugins | Local plugins work; cloud plugins show offline state. |

## Cross-Platform Support

| Platform | Requirement |
|---|---|
| Windows | Full support, signed installer, auto-update. |
| macOS | Full support, notarized universal builds for Apple Silicon and Intel if needed. |
| Linux | AppImage or deb/rpm support; auto-update where feasible. |

