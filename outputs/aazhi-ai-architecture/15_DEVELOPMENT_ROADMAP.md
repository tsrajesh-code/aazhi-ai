# 15. Development Roadmap

## Phase Overview

| Phase | Name | Goal | Difficulty |
|---:|---|---|---|
| 1 | Foundation MVP | Desktop shell, chat, local API, model manager, basic memory. | High |
| 2 | Workspace and Coding | Project workspaces, file explorer, indexing, coding assistant. | High |
| 3 | Creative and Voice | Image generation/editing, voice input/output, asset library. | Medium-High |
| 4 | Agents and Plugins | Permissioned agents, plugin SDK, official integrations. | Very High |
| 5 | Scale and Enterprise | Sync, collaboration, admin, marketplace, compliance readiness. | Very High |

## Phase 1: Foundation MVP

| Area | Deliverables |
|---|---|
| Desktop | Electron app shell, secure preload, routing, settings. |
| Backend | FastAPI local service, OpenAPI contracts, service supervision. |
| Chat | Conversations, streaming responses, history, model selector. |
| Models | Ollama integration, cloud provider adapter, model registry. |
| Memory | Basic user and conversation memory with inspect/delete controls. |
| Storage | Local relational store, vector store, migrations. |
| Security | Secret storage, basic permission broker, audit logs. |

## Phase 2: Workspace and Coding

| Area | Deliverables |
|---|---|
| Workspace | Project creation, file explorer, workspace settings. |
| Indexing | File chunking, embeddings, semantic search, ignored paths. |
| Coding | Explain code, generate snippets, review files, suggest tests. |
| Context | Context picker, citations, file source tracking. |
| UX | Dashboard, command palette, right inspector. |

## Phase 3: Creative and Voice

| Area | Deliverables |
|---|---|
| Image | Text-to-image, image editing, variations, asset library. |
| Voice | Speech-to-text, text-to-speech, voice sessions. |
| Jobs | Background job queue, progress, retries, cancellation. |
| Prompt library | Reusable prompts for chat, code, image, and voice. |

## Phase 4: Agents and Plugins

| Area | Deliverables |
|---|---|
| Agents | Goal planning, approval gates, execution logs, task memory. |
| Tool broker | Unified tool permission and audit system. |
| Plugin SDK | Manifest, runtime, APIs, example plugins. |
| Official plugins | GitHub, Docker, Browser, Figma prototypes. |
| Security | Plugin sandbox hardening, signing, permission UI. |

## Phase 5: Scale and Enterprise

| Area | Deliverables |
|---|---|
| Cloud sync | Account, device sync, encrypted backups. |
| Collaboration | Shared workspaces, comments, team memory. |
| Enterprise | SSO, RBAC, audit exports, retention policies. |
| Marketplace | Signed plugin distribution and publisher portal. |
| Operations | Observability, release channels, staged rollout. |

## Difficulty Notes

| Area | Risk |
|---|---|
| Agent execution | High risk due to safety, permissions, and user trust. |
| Plugin ecosystem | High risk due to API stability and sandboxing. |
| Memory | Product-sensitive due to privacy and perceived creepiness. |
| Local models | Support burden across hardware and OS differences. |
| Image/voice | Provider differences, local GPU constraints, asset management. |

