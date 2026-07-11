# 16. Documentation Guide

## README Structure

Recommended `README.md` sections:

| Section | Purpose |
|---|---|
| Product overview | What AAZHI AI is and who it serves. |
| Current status | Planning, alpha, beta, stable, or experimental. |
| Features | Core capabilities and release status. |
| Architecture summary | High-level system diagram and module boundaries. |
| Getting started | Setup steps for developers. |
| Development workflow | Running desktop app, backend, tests, and linters. |
| Project structure | Link to folder structure documentation. |
| Security | Reporting vulnerabilities and handling secrets. |
| Contributing | Link to contribution guide. |
| License | Product license and third-party notices. |

## Architecture Guide

Recommended `docs/architecture/` contents:

| Document | Contents |
|---|---|
| `overview.md` | System diagram, architecture principles, module map. |
| `desktop.md` | Electron shell, renderer, preload, IPC rules. |
| `backend.md` | FastAPI services, workers, API contracts. |
| `ai.md` | Model manager, prompts, context, routing, evaluations. |
| `memory.md` | Memory types, vector search, privacy controls. |
| `plugins.md` | SDK, manifest, permissions, sandbox. |
| `security.md` | Threat model, auth, encryption, audit. |
| `database.md` | Schema, migrations, indexes, retention. |
| `adr/` | Architecture decision records. |

## Developer Guide

Recommended topics:

| Topic | Description |
|---|---|
| Local environment | Required tools, Node, Python, databases, Ollama. |
| Running the app | Desktop shell, backend service, workers. |
| API contracts | How OpenAPI clients are generated and validated. |
| Adding a model provider | Adapter interface, tests, capability metadata. |
| Adding memory features | Store, retrieval, permissions, UI requirements. |
| Adding a plugin | Manifest, SDK usage, permissions, testing. |
| Adding UI screens | Component conventions, routing, accessibility. |
| Testing | Unit, integration, E2E, security, AI evals. |
| Release process | Versioning, changelog, signing, packaging, auto-update. |

## Contribution Guide

Recommended `CONTRIBUTING.md` sections:

| Section | Description |
|---|---|
| Code of conduct | Expected community behavior. |
| Issue workflow | Bug reports, feature requests, security reports. |
| Branch strategy | Feature branches and release branches. |
| Pull request checklist | Tests, docs, screenshots, migrations, security review. |
| Review process | Required reviewers by area. |
| Commit style | Conventional commits recommended. |
| Plugin contribution | Additional plugin review and permission checks. |

## Coding Standards

| Area | Standard |
|---|---|
| TypeScript | Strict mode, typed API contracts, no unsafe renderer access. |
| React | Functional components, accessible primitives, clear state boundaries. |
| Python | Type hints, service boundaries, repository pattern, async where useful. |
| APIs | OpenAPI-first, consistent errors, pagination, idempotency for jobs. |
| Database | Migrations required, indexes for new query patterns. |
| Security | Secrets never logged, permission checks for sensitive operations. |
| Testing | Tests required for behavior, migrations, permissions, and provider adapters. |
| Documentation | Update docs for public contracts and architecture decisions. |

## Architecture Decision Records

Use ADRs for decisions such as:

| Decision | Example |
|---|---|
| Desktop framework | Electron selected over native alternatives. |
| Backend runtime | FastAPI selected for AI ecosystem. |
| Vector database | ChromaDB selected for local-first MVP. |
| Plugin sandbox | Runtime isolation strategy. |
| Memory defaults | Privacy and approval policy. |
| Cloud sync | Encryption and conflict model. |

