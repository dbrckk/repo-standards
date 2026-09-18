# AI context standard

Every active repository should expose a compact machine-readable context layer under `.ai/`.

## Reading order

1. `.ai/project-state.md` — persistent manual state plus automatic Git state.
2. `.ai/change-impact.md` — latest changed files and affected areas.
3. `.ai/architecture.json` — project types, modules and entrypoint candidates.
4. `.ai/commands.json` — detected validation commands.
5. `.ai/repo-health.md` — repository-level health signals.
6. `.ai/repo-map.md` — compressed source context, used only when smaller context is insufficient.

Agents should start from the smallest relevant context and expand only when necessary.

## Generated context requirements

Generated context must exclude vendor dependencies, build outputs, caches, large assets, binaries, generated code when practical, and the `.ai/` directory itself.

Generated files should be deterministic, concise, safe to commit, and must never include secrets.

## Change scope

When `.ai/change-impact.md` exists, agents should inspect the affected areas before exploring unrelated modules. Direct test candidates are hints, not proof of complete test coverage.
