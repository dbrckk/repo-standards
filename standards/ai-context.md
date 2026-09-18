# AI context standard

Every active repository should expose a compact machine-readable context layer under `.ai/`.

## Reading order

1. `.ai/project-state.md` — persistent manual state plus automatic Git state.
2. `.ai/change-impact.md` — latest changed files and affected areas.
3. `.ai/architecture.json` — project types, source roots and entrypoint candidates.
4. `.ai/brain/summary.md` — smallest symbol-oriented repository overview.
5. `.ai/brain/lookup.json` — compact symbol-name to file/line locator.
6. `.ai/brain/code-graph.json` and `.ai/brain/imports.json` — static internal relationships.
7. `.ai/dependency-map.json` — manifests, external dependencies and internal roots.
8. `.ai/commands.json` — detected validation commands.
9. `.ai/ci-status.md` — recent non-standards CI results.
10. `.ai/security-signals.json` — heuristic secret/risky-file signals without secret values.
11. `.ai/repo-health.md` — repository-level health signals.
12. `.ai/index.md` — routing to segmented maps.
13. `.ai/maps/<area>.md` — area-specific compressed context when symbol routing is insufficient.
14. `.ai/repo-map.md` — full compressed source context as final fallback.

Agents should start from the smallest relevant context and expand only when necessary.

Repo Brain symbol hits are locators, not source-of-truth replacements. Always verify the underlying source before editing.

Generated context must exclude vendor dependencies, build outputs, caches, large assets, binaries, generated code when practical, and the `.ai/` directory itself.

Generated files should be deterministic, concise, safe to commit, and must never include secret values.
