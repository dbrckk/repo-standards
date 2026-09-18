# AI context standard

Every active repository should expose a compact machine-readable context layer under `.ai/`.

## Reading order

1. `.ai/project-state.md` — persistent manual state plus automatic Git state.
2. `.ai/brain/impact.json` — changed source files, reverse-import impact, impacted symbols and selected tests.
3. `.ai/brain/selected-tests.json` — targeted test files and candidate commands.
4. `.ai/change-impact.md` — broader repository-level change summary.
5. `.ai/architecture.json` — project types, source roots and entrypoint candidates.
6. `.ai/brain/summary.md` and `.ai/brain/incremental-state.json` — compact routing plus index freshness/mode.
7. `.ai/brain/capabilities.json` and AST shards — exact symbol/member ranges when ast-grep is available.
8. `.ai/brain/lookup.json` — portable symbol fallback.
9. `.ai/brain/code-graph.json` and `.ai/brain/imports.json` — static internal relationships.
10. `.ai/dependency-map.json` — manifests, external dependencies and internal roots.
11. `.ai/commands.json` — detected broad validation commands.
12. `.ai/ci-status.md` — recent non-standards CI results.
13. `.ai/security-signals.json` — heuristic secret/risky-file signals without secret values.
14. `.ai/repo-health.md` — repository-level health signals.
15. `.ai/index.md` and segmented maps — larger area context only when symbol-level context is insufficient.
16. `.ai/repo-map.md` — full compressed source context as final fallback.

## Incremental rules

Repo Brain should reuse the previous committed index when its stored `indexed_head` is an ancestor of the current commit and the diff remains small.

A full rebuild must be used automatically when prior state is missing, divergent, unreadable, or the changed set exceeds the configured threshold.

Targeted tests are hints. Verify their commands against project tooling and expand validation when the impact graph is incomplete, a targeted test fails, or release-sensitive work requires broader coverage.

Generated files must be deterministic, concise, safe to commit, and must never include secret values.
