# Global agent standards

These rules are intended to be inherited by repositories using dbrckk/repo-standards.

## Context first
1. Read `.ai/project-state.md` when present.
2. Read `.ai/change-impact.md` to identify the smallest relevant scope.
3. Read `.ai/architecture.json` for project shape and entrypoint candidates.
4. Read `.ai/commands.json` before choosing validation commands.
5. Read `.ai/repo-health.md` for repository-level signals.
6. Read `.ai/repo-map.md` only when the smaller context files are insufficient.
7. Fetch only the files, symbols, diffs, and line ranges needed for the task.
8. Do not scan generated, vendor, cache, build, asset, or binary directories unless the task explicitly concerns them.

## Work order
1. Restore current project state.
2. Start from the changed/affected areas.
3. Identify blockers and regressions before adding features.
4. Make the smallest coherent change.
5. Preserve architecture and public interfaces unless the task requires otherwise.
6. Run the relevant test, lint, build, and validation commands.
7. Inspect the final diff.
8. Update manual project state when status, blockers, or next priority materially changes.

## Quality
- Do not leave placeholder implementations, fake success paths, or avoidable TODOs in completed work.
- Prefer deterministic commands and reproducible workflows.
- Never commit secrets or credentials.
- Keep AI-generated context concise enough to be useful.
