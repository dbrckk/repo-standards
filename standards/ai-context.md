# AI context standard

Every active repository should expose a compact machine-readable context layer under `.ai/`.

## Reading order

1. `.ai/session-state.json` — active task checkpoint when present.
2. `.ai/project-state.md` — persistent manual state plus automatic Git state.
3. `.ai/brain/hotset.json` — bounded list of recently relevant files.
4. `.ai/brain/context-manifest.json` plus one relevant packet under `.ai/brain/context/`.
5. `.ai/brain/graph-index.json` — compact dependency-routing summary and central files.
6. Relevant `.ai/brain/graph-shards/<area>.json` — bounded dependency graph for one area.
7. `.ai/brain/reverse-deps.json` — direct dependencies and dependents per file.
8. `.ai/brain/impact.json` — changed source files, reverse-import impact, impacted symbols and selected tests.
6. `.ai/brain/selected-tests.json` — targeted test files and candidate commands.
7. `.ai/change-impact.md` — broader repository-level change summary.
8. `.ai/architecture.json` — project types, source roots and entrypoint candidates.
9. `.ai/brain/summary.md` and `.ai/brain/incremental-state.json` — compact routing plus index freshness/mode.
10. `.ai/brain/capabilities.json` and AST shards — exact symbol/member ranges when ast-grep is available.
11. `.ai/brain/lookup.json` — portable symbol fallback.
12. `.ai/brain/code-graph.json` and `.ai/brain/imports.json` — static internal relationships.
13. `.ai/dependency-map.json` — manifests, external dependencies and internal roots.
14. `.ai/commands.json` — detected broad validation commands.
15. `.ai/ci-status.md` — recent non-standards CI results.
16. `.ai/security-signals.json` — heuristic secret/risky-file signals without secret values.
17. `.ai/repo-health.md` — repository-level health signals.
18. `.ai/index.md` and segmented maps — larger area context only when bounded context is insufficient.
19. `.ai/repo-map.md` — full compressed source context as final fallback.

## Context budgets

Agents should begin with the smallest useful context. The default Repo Brain v6 hotset is bounded to 32 files and area packets to 16 files. Source files outside that set should be fetched only when the current task or authoritative references justify expansion.

## Incremental rules

Repo Brain should reuse the previous committed index when its stored `indexed_head` is an ancestor of the current commit and the diff remains small.

A full rebuild must be used automatically when prior state is missing, divergent, unreadable, or the changed set exceeds the configured threshold.

Hash-cache entries may be reused for unchanged hotset files to avoid redundant parsing or summarization.

Targeted tests are hints. Verify their commands against project tooling and expand validation when the impact graph is incomplete, a targeted test fails, or release-sensitive work requires broader coverage.

Generated files must be deterministic, concise, safe to commit, and must never include secret values.
