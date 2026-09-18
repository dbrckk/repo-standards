# Releases

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
