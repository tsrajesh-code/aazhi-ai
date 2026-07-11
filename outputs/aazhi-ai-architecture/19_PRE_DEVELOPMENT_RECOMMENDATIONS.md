# 19. Recommendations Before Development Begins

## Highest-Priority Decisions

| Decision | Recommendation |
|---|---|
| MVP scope | Start with chat, model manager, local/cloud model routing, workspace files, and transparent memory. |
| Plugin timing | Keep plugins private/internal until the permission broker and sandbox are mature. |
| Agent timing | Ship agents after file permissions, audit logs, and approval UX are proven. |
| Local database | Use SQLite for local-first MVP and design schemas to map cleanly to PostgreSQL later. |
| Vector store | Start with ChromaDB behind an abstraction so pgvector or Qdrant can replace it later. |
| Cloud sync | Do not include sync in the earliest MVP unless the team can support security and conflict resolution well. |

## Product Recommendations

| Area | Recommendation |
|---|---|
| Positioning | Present AAZHI AI as a professional AI workspace, not only a chatbot. |
| Tamil identity | Make the identity meaningful and elegant; avoid overloading the UI with cultural motifs. |
| Onboarding | Ask users to choose privacy posture: local-first, balanced, or cloud-enhanced. |
| Memory | Make memory visible from day one. Add "remember", "forget", and "do not remember" actions in chat. |
| Models | Give users practical defaults. Advanced model configuration should exist but not dominate onboarding. |
| Trust | Show which model, memories, files, and tools were used in a response. |

## Architecture Recommendations

| Area | Recommendation |
|---|---|
| Contracts | Use OpenAPI and generated clients early to prevent frontend/backend drift. |
| Boundaries | Keep AI orchestration separate from individual features. |
| Workers | Move embeddings, indexing, image generation, and voice processing into background jobs. |
| Events | Use internal events for audit logs, memory extraction, and job updates. |
| Migrations | Treat local schema migrations as a first-class release concern. |
| Evaluations | Build a small AI regression suite before prompts become difficult to change. |

## Security Recommendations

| Area | Recommendation |
|---|---|
| Secrets | Use OS keychain from the first build. |
| Renderer | Keep renderer untrusted; expose only narrow preload APIs. |
| Logs | Redact prompts, keys, paths, and secrets by default. |
| Permissions | Build permission broker before agents and plugins. |
| Updates | Plan code signing and signed updates before public beta. |
| Data export | Provide export/delete options early to build user trust. |

## UX Recommendations

| Area | Recommendation |
|---|---|
| First screen | Use the real workspace/dashboard experience, not a marketing landing page. |
| Information density | Keep UI professional and efficient for daily use. |
| Chat | Make context and memory inspectable without overwhelming the main conversation. |
| Image studio | Keep generation controls powerful but visually organized. |
| Accessibility | Include keyboard, contrast, and screen reader checks in the design system. |

## Team Recommendations

| Role | Early Responsibility |
|---|---|
| Product lead | MVP scope, onboarding, privacy posture, release criteria. |
| Principal architect | Package boundaries, contracts, storage, plugin and agent safety. |
| AI engineer | Model adapters, prompt manager, context builder, eval harness. |
| Security engineer | Threat model, sandbox, permission broker, secret management. |
| UI/UX designer | Design system, navigation, chat, memory, settings, accessibility. |
| DevOps engineer | CI, packaging, signing, release channels, diagnostics. |

## Suggested Build Order

1. Desktop shell and local backend.
2. Chat with model manager.
3. Secure settings and secret storage.
4. Local persistence and conversation history.
5. Memory dashboard and retrieval.
6. Workspace file permissions and indexing.
7. Coding assistant.
8. Image studio.
9. Voice assistant.
10. Permissioned agents.
11. Plugin SDK.
12. Cloud sync and collaboration.

