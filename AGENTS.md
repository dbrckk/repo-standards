# Global agent standards

These rules are intended to be inherited by repositories using dbrckk/repo-standards.

## Context first
1. Read `.ai/project-state.md` when present.
2. Read `.ai/change-impact.md` to identify the smallest relevant scope.
3. Read `.ai/architecture.json` for project shape and entrypoint candidates.
4. Read `.ai/dependency-map.json` when the change may cross module or package boundaries.
5. Read `.ai/commands.json` before choosing validation commands.
6. Read `.ai/ci-status.md` for recent CI state.
7. Read `.ai/security-signals.json` before security-sensitive or release work.
8. Read `.ai/repo-health.md` for repository-level signals.
9. Read `.ai/index.md` and prefer the relevant segmented map.
10. Read `.ai/repo-map.md` only when the smaller context files are insufficient.
11. Fetch only the files, symbols, diffs, and line ranges needed for the task.

## Work order
1. Restore current project state.
2. Start from the changed/affected areas.
3. Identify blockers and regressions before adding features.
4. Check CI and security signals when relevant.
5. Make the smallest coherent change.
6. Preserve architecture and public interfaces unless the task requires otherwise.
7. Run the relevant test, lint, build, and validation commands.
8. Inspect the final diff.
9. Update manual project state when status, blockers, or next priority materially changes.

## Quality
- Do not leave placeholder implementations, fake success paths, or avoidable TODOs in completed work.
- Prefer deterministic commands and reproducible workflows.
- Never commit secrets or credentials.
- Treat security signals as heuristics that require verification, not proof of a vulnerability.
- Keep AI-generated context concise enough to be useful.
