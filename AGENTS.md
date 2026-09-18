# Global agent standards

These rules are intended to be inherited by repositories using dbrckk/repo-standards.

## Context first
1. Read `.ai/project-state.md` when present.
2. Read `.ai/repo-health.md` when present.
3. Read `.ai/repo-map.md` before broad repository exploration.
4. Fetch only the files, symbols, diffs, and line ranges needed for the task.
5. Do not scan generated, vendor, cache, build, asset, or binary directories unless the task explicitly concerns them.

## Work order
1. Restore current project state.
2. Identify blockers and regressions before adding features.
3. Make the smallest coherent change.
4. Preserve architecture and public interfaces unless the task requires otherwise.
5. Run the relevant test, lint, build, and validation commands.
6. Inspect the final diff.
7. Update project state when the repository's status or next priority materially changes.

## Quality
- Do not leave placeholder implementations, fake success paths, or avoidable TODOs in completed work.
- Prefer deterministic commands and reproducible workflows.
- Never commit secrets or credentials.
- Keep AI-generated context concise enough to be useful.
