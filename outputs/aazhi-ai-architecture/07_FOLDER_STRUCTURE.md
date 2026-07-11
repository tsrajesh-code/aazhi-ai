# 7. Folder Structure

## Monorepo Recommendation

AAZHI AI should use a monorepo so the desktop app, backend services, plugin SDK, documentation, tests, and shared contracts evolve together.

```text
aazhi-ai/
  apps/
    desktop/
      electron/
      renderer/
      preload/
      assets/
      tests/
    local-api/
      app/
      migrations/
      workers/
      tests/
  packages/
    ui/
    design-system/
    shared-types/
    api-client/
    plugin-sdk/
    prompt-library/
    config/
  services/
    cloud-api/
    sync-service/
    marketplace-service/
    auth-service/
  plugins/
    official/
      github/
      docker/
      browser/
      figma/
    examples/
  models/
    manifests/
    benchmarks/
    evals/
  docs/
    architecture/
    product/
    security/
    api/
    developer/
    operations/
  tests/
    e2e/
    fixtures/
    security/
    performance/
  scripts/
    dev/
    build/
    release/
    database/
  infrastructure/
    docker/
    terraform/
    kubernetes/
    observability/
  .github/
    workflows/
    ISSUE_TEMPLATE/
    PULL_REQUEST_TEMPLATE.md
  README.md
  TASKS.md
  ROADMAP.md
```

## Key Directories

| Directory | Purpose |
|---|---|
| `apps/desktop` | Electron shell, React renderer, preload bridge, desktop assets. |
| `apps/local-api` | FastAPI backend that runs locally with the desktop app. |
| `packages/ui` | Shared production UI components. |
| `packages/design-system` | Tokens, themes, typography, colors, icons, accessibility rules. |
| `packages/shared-types` | Shared TypeScript types and generated API contracts. |
| `packages/api-client` | Generated frontend client from OpenAPI. |
| `packages/plugin-sdk` | Public SDK for official and third-party plugin authors. |
| `packages/prompt-library` | Versioned prompts, templates, and model behavior configs. |
| `services` | Future cloud services for sync, marketplace, identity, and collaboration. |
| `plugins/official` | First-party plugins maintained by AAZHI AI. |
| `models` | Model manifests, routing metadata, benchmarks, and evaluations. |
| `docs` | Product, architecture, security, API, and developer documentation. |
| `tests` | Cross-cutting tests that span packages and apps. |
| `infrastructure` | Future cloud and deployment infrastructure. |

## Package Boundaries

| Package | May Depend On | Must Not Depend On |
|---|---|---|
| Desktop renderer | UI, shared types, API client | Backend internals, secrets, filesystem directly |
| Electron main | Shared types, config | React internals |
| Local API | Prompt library, model manifests | Renderer code |
| Plugin SDK | Shared types | First-party plugin implementations |
| Official plugins | Plugin SDK | Local API internals unless exposed through SDK |

## Naming Standards

| Item | Convention |
|---|---|
| TypeScript files | `kebab-case.ts` or `PascalCase.tsx` for components. |
| Python modules | `snake_case.py`. |
| Database migrations | Timestamped and descriptive. |
| API routes | Resource-oriented names: `/workspaces`, `/conversations`, `/models`. |
| Feature packages | Domain names: `memory`, `models`, `plugins`, `agents`. |

