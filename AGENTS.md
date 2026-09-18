# Global agent standards

These rules are intended to be inherited by repositories using dbrckk/repo-standards.

## Context first
1. Read `.ai/project-state.md` when present.
2. Read `.ai/brain/impact.json` for changed source files, reverse-import impact, impacted symbols, and selected tests.
3. Read `.ai/brain/selected-tests.json` before choosing validation scope.
3. Read `.ai/brain/references.json` and `.ai/brain/symbol-dependencies.json` for changed-symbol routing.
4. Read `.ai/change-impact.md` for the broader repository-level change summary.
5. Read `.ai/architecture.json` for project shape and entrypoint candidates.
6. Read `.ai/brain/summary.md`, `.ai/brain/incremental-state.json`, and `.ai/brain/capabilities.json`.
7. When `ast_grep_outline` is true, use `.ai/brain/ast-routing.json` and the relevant `.ai/brain/ast-symbols/<initial>.json` shard for exact symbol/member ranges.
8. If AST routing is unavailable or has no useful hit, fall back to `.ai/brain/lookup.json`.
9. Use `.ai/brain/code-graph.json` and `.ai/brain/imports.json` when changes may cross module boundaries.
10. Read `.ai/dependency-map.json` when package/dependency context matters.
11. Read `.ai/commands.json` before broad validation.
12. Read `.ai/ci-status.md` for recent CI state.
13. Read `.ai/security-signals.json` before security-sensitive or release work.
14. Read `.ai/repo-health.md` for repository-level signals.
15. Read `.ai/index.md` and prefer the relevant segmented map only if symbol-level context is insufficient.
16. Read `.ai/repo-map.md` only when smaller context files are insufficient.
17. Fetch only the files, symbols, diffs, and line ranges needed for the task.

## Work order
1. Restore current project state.
2. Start from Repo Brain impact and targeted-test selection.
3. Route to exact symbol ranges when available.
4. Verify the authoritative source around the located symbol.
5. Identify blockers and regressions before adding features.
6. Prefer targeted tests first; expand validation when impact is ambiguous or targeted tests fail.
7. Check CI and security signals when relevant.
8. Make the smallest coherent change.
9. Preserve architecture and public interfaces unless the task requires otherwise.
10. Inspect the final diff.
11. Update manual project state when status, blockers, or next priority materially changes.

## Quality
- Do not leave placeholder implementations, fake success paths, or avoidable TODOs in completed work.
- Prefer deterministic commands and reproducible workflows.
- Never commit secrets or credentials.
- Treat impact edges, selected tests, ast-grep Outline, Repo Brain relationships, and security signals as static heuristics that require source/tool verification.
- Keep AI-generated context concise enough to be useful.
