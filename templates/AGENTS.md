# Repository agent instructions

This repository adopts shared standards from `dbrckk/repo-standards` at the release recorded in `.repo-standards.yml`.

Before substantial work:
1. Read the central `AGENTS.md` and relevant standards at the configured ref.
2. Read `.ai/session-state.json` when present.
3. Read `.ai/project-state.md`.
4. Read `.ai/brain/hotset.json`.
5. Read `.ai/brain/search-manifest.json` and only the needed `.ai/brain/search-shards/<initial>.json` shard for exact task terms.
6. Reuse `.ai/brain/query-cache.json` when its fingerprint still matches current context.
7. Read `.ai/brain/context-manifest.json` and only the relevant `.ai/brain/context/<area>.json` packet.
6. Read `.ai/brain/graph-index.json` and the relevant `.ai/brain/graph-shards/<area>.json` when dependency routing matters.
7. Use `.ai/brain/reverse-deps.json` for upstream/downstream file impact.
8. Read `.ai/brain/impact.json` and `.ai/brain/selected-tests.json`.
9. Read `.ai/brain/references.json` and `.ai/brain/symbol-dependencies.json` only when symbol routing requires them.
10. Read `.ai/change-impact.md` and `.ai/architecture.json` when broader structure is needed.
11. Read `.ai/brain/summary.md`, `.ai/brain/incremental-state.json`, and `.ai/brain/capabilities.json` when index freshness/capabilities matter.
12. If ast-grep enrichment is available, route named symbols through `.ai/brain/ast-routing.json` and one `.ai/brain/ast-symbols/<initial>.json` shard.
13. Fall back to `.ai/brain/lookup.json` when AST routing is unavailable or insufficient.
14. Use `.ai/brain/code-graph.json` and `.ai/brain/imports.json` for cross-module context.
15. Read `.ai/dependency-map.json` when dependency context matters.
16. Read `.ai/commands.json`, `.ai/ci-status.md`, and security signals when relevant.
17. Read `.ai/repo-health.md`.
18. Use `.ai/index.md` and segmented maps only if bounded context is insufficient.
19. Read `.ai/repo-map.md` only as a final broad-context fallback.
20. Fetch only task-relevant source files or line ranges.

Repository-specific rules:
- Preserve existing architecture and public interfaces unless the task requires a change.
- Prefer the smallest coherent change.
- Prefer targeted tests from `.ai/brain/selected-tests.json`; expand validation when impact is ambiguous or targeted tests fail.
- Treat hotset/context packets and graph shards as routing hints, not authoritative source.
- Verify reference/dependency/impact/AST hits against authoritative source before editing.
- Treat security signals and static graph edges as heuristics, not proof.
- Never reproduce suspected secret values.
- Update manual project-state sections when status, blockers, or next priority materially changes.
- Maintain `.ai/session-state.json` for substantial multi-turn work so a later "Continue" can resume without reconstructing the repository.


Context budget policy:
- Start with the confidence-based context budget produced by Repo Brain.
- High confidence: inspect up to 3 files.
- Medium confidence: inspect up to 6 files.
- Low confidence: inspect up to 12 files.
- Expand only when evidence from the current tier is insufficient.


Learning feedback policy:
- After a substantial task, record which files were actually useful, which routed files were unnecessary, and which tests were used.
- Store deterministic feedback in `.ai/brain/routing-learning.json`.
- Treat learned scores as routing hints only; always verify authoritative source before editing.


Automatic learning policy:
- After a successful repository-intelligence refresh with real source changes, allow Repo Brain to learn positive routing feedback from the changed source files.
- Automatic negative feedback is only allowed when a prior task route exactly matches the active task.
- Record the decision in `.ai/brain/auto-learning.json`.
- Selected tests are hints only unless a separate validation step confirms execution.


Validation memory policy:
- After actually running a targeted test, record its result in `.ai/brain/validation-memory.json`.
- Passed tests increase future test-routing preference for similar task terms; failed tests reduce it.
- Never mark a test as passed unless an execution result confirmed success.
- Selected-but-not-run tests remain hints only.


Stability policy:
- Treat Repo Brain regression tests as a hard gate for generated context.
- Read `.ai/brain/benchmark.json` when diagnosing routing slowness or excessive context size.
- Prefer fixing measured regressions over adding new indexing layers.
