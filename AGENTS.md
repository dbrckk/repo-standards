# Global agent standards

These rules are intended to be inherited by repositories using dbrckk/repo-standards.

## Context first
1. Read `.ai/project-state.md` when present.
2. Read `.ai/change-impact.md` to identify the smallest relevant scope.
3. Read `.ai/architecture.json` for project shape and entrypoint candidates.
4. Read `.ai/brain/summary.md` for the compact symbol-oriented overview.
5. Search `.ai/brain/lookup.json` for named classes, functions, methods, or symbols before opening broad source files.
6. Read `.ai/brain/code-graph.json` and `.ai/brain/imports.json` when changes may cross module boundaries.
7. Read `.ai/dependency-map.json` when package/dependency context matters.
8. Read `.ai/commands.json` before choosing validation commands.
9. Read `.ai/ci-status.md` for recent CI state.
10. Read `.ai/security-signals.json` before security-sensitive or release work.
11. Read `.ai/repo-health.md` for repository-level signals.
12. Read `.ai/index.md` and prefer the relevant segmented map only if symbol-level context is insufficient.
13. Read `.ai/repo-map.md` only when smaller context files are insufficient.
14. Fetch only the files, symbols, diffs, and line ranges needed for the task.

## Work order
1. Restore current project state.
2. Route by change impact and symbol lookup.
3. Verify the authoritative source around the located symbol.
4. Identify blockers and regressions before adding features.
5. Check CI and security signals when relevant.
6. Make the smallest coherent change.
7. Preserve architecture and public interfaces unless the task requires otherwise.
8. Run the relevant test, lint, build, and validation commands.
9. Inspect the final diff.
10. Update manual project state when status, blockers, or next priority materially changes.

## Quality
- Do not leave placeholder implementations, fake success paths, or avoidable TODOs in completed work.
- Prefer deterministic commands and reproducible workflows.
- Never commit secrets or credentials.
- Treat Repo Brain relationships and security signals as static heuristics that require source verification.
- Keep AI-generated context concise enough to be useful.
