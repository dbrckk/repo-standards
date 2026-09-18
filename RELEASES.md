# Releases

## v10

Repo Brain v5 / incremental AST references:

- upgrades Repo Brain to v5;
- reparses ast-grep Outline only for changed source files in incremental mode;
- preserves prior AST shards and merges refreshed files;
- generates references.json for changed-symbol lexical occurrences;
- generates symbol-dependencies.json for bounded dependency hints;
- preserves portable fallback, targeted tests, and unified single-commit context.

## v9

Repo Brain v4 / incremental impact:

- upgrades Repo Brain to v4;
- reuses prior committed symbol/import indexes for small diffs;
- reparses only changed source files when incremental state is valid;
- automatically falls back to a full rebuild when state is missing, divergent, unreadable, or the diff is too large;
- generates .ai/brain/impact.json with changed source, reverse-import impact and impacted symbols;
- generates .ai/brain/selected-tests.json with likely targeted test files and candidate commands;
- preserves v8 AST shard routing and unified single-commit context.

## v8

Repo Brain v3 / ast-grep routing:

- upgrades Repo Brain to v3;
- adds optional ast-grep Outline enrichment with portable fallback;
- records exact symbol/member start and end ranges;
- shards AST symbol lookup by initial to avoid monolithic index reads;
- groups file outlines by repository area;
- keeps Repo Brain outside the critical path by running it in parallel;
- preserves one unified AI-context commit.

## v7

Repo Brain integration:

- adds dbrckk/repo-brain v2 as a sixth parallel context generator;
- produces compact symbol lookup, full symbol index, imports and a lightweight internal code graph;
- routes agents through symbol lookup before segmented or full Repomix maps;
- merges Repo Brain output into the same unified single AI-context commit;
- preserves the parallel artifact architecture introduced in v6.

## v6

Unified single-commit repository standards:

- runs repo map, health, project state, context intelligence, and observability generators in parallel;
- transfers generated context through GitHub Actions artifacts;
- validates all generated context before writing;
- performs one final `chore(ai): refresh unified AI context` commit;
- avoids repeated AI commits that can retrigger unrelated CI workflows;
- preserves v5 context, security, dependency, CI, and segmented-map capabilities.

## v5

Stable repository standards with:

- compact Repomix context and segmented maps for large repositories;
- persistent project state;
- repository health report;
- architecture and change-impact context;
- detected validation commands;
- CI summary;
- heuristic security signals without secret values;
- lightweight dependency mapping;
- concurrency cancellation;
- pinned official GitHub Actions by immutable SHA.

## v4

Added context intelligence and segmented repository maps.

## v3

Introduced stable version pinning and persistent project-state continuity.

## Development policy

`main` is the development branch for the next version. Consumer repositories should reference a stable release branch such as `v5`.
