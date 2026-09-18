# Global agent standards

These rules are intended to be inherited by repositories using dbrckk/repo-standards.

## Context first
1. Read `.ai/project-state.md` when present.
2. Read `.ai/brain/impact.json`.
3. Read `.ai/brain/selected-tests.json`.
4. Read `.ai/brain/references.json` for changed-symbol occurrences.
5. Read `.ai/brain/symbol-dependencies.json` for bounded dependency hints.
6. Read `.ai/change-impact.md`.
7. Read `.ai/architecture.json`.
8. Read `.ai/brain/summary.md`, `.ai/brain/incremental-state.json`, and `.ai/brain/capabilities.json`.
9. When ast-grep enrichment is available, route named symbols through `.ai/brain/ast-routing.json` and one `.ai/brain/ast-symbols/<initial>.json` shard.
10. Fall back to `.ai/brain/lookup.json` when AST routing is unavailable or insufficient.
11. Use `.ai/brain/code-graph.json` and `.ai/brain/imports.json` for cross-module context.
12. Read `.ai/dependency-map.json` when package/dependency context matters.
13. Read `.ai/commands.json`, `.ai/ci-status.md`, and security signals when relevant.
14. Read `.ai/repo-health.md`.
15. Use `.ai/index.md` and segmented maps only if symbol-level context is insufficient.
16. Read `.ai/repo-map.md` only as a final broad-context fallback.
17. Fetch only task-relevant source files or line ranges.

## Work order
1. Restore current project state.
2. Start from impact, targeted tests, references, and symbol dependencies.
3. Route to exact symbol ranges when available.
4. Verify authoritative source around every located symbol.
5. Prefer targeted tests first; expand validation when impact is ambiguous or targeted tests fail.
6. Make the smallest coherent change.
7. Preserve architecture and public interfaces unless the task requires otherwise.
8. Inspect the final diff and update manual project state when materially changed.

## Quality
- Treat references, dependencies, impact edges, selected tests, AST output, and security signals as static heuristics requiring verification.
- Never commit or reproduce secrets.
- Prefer deterministic and reproducible workflows.
