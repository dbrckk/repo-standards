# AI context standard

Every active repository should expose a compact machine-readable context layer under `.ai/`.

## Reading order

1. `.ai/project-state.md` — persistent manual state plus automatic Git state.
2. `.ai/change-impact.md` — latest changed files and affected areas.
3. `.ai/architecture.json` — project types, source roots and entrypoint candidates.
4. `.ai/dependency-map.json` — manifests, external dependencies and internal roots.
5. `.ai/commands.json` — detected validation commands.
6. `.ai/ci-status.md` — recent non-standards CI results.
7. `.ai/security-signals.json` — heuristic secret/risky-file signals without secret values.
8. `.ai/repo-health.md` — repository-level health signals.
9. `.ai/index.md` — routing to segmented maps.
10. `.ai/maps/<area>.md` — area-specific compressed context when available.
11. `.ai/repo-map.md` — full compressed source context, used only when smaller context is insufficient.

Agents should start from the smallest relevant context and expand only when necessary.

## Generated context requirements

Generated context must exclude vendor dependencies, build outputs, caches, large assets, binaries, generated code when practical, and the `.ai/` directory itself.

Generated files should be deterministic, concise, safe to commit, and must never include secret values.

## Change scope

When `.ai/change-impact.md` exists, agents should inspect the affected areas before exploring unrelated modules. Direct test candidates are hints, not proof of complete test coverage.

## Security signals

`.ai/security-signals.json` is deliberately heuristic. It may contain false positives and must never contain matched secret values. A signal should trigger targeted inspection, not an automatic claim that a credential is exposed.
