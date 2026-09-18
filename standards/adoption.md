# Adoption standard

A repository adopts the central standards when it contains:

- `.repo-standards.yml` pointing to `dbrckk/repo-standards`.
- `AGENTS.md` instructing agents to load the shared standards first.
- `.github/workflows/ai-repo-map.yml` calling the reusable workflows.
- `.ai/project-state.md` for persistent project continuity.

Generated files `.ai/repo-map.md` and `.ai/repo-health.md` are maintained by GitHub Actions.

For new repositories, copy the files from `templates/`. Repository-specific rules may extend the shared rules but should not silently duplicate or contradict them.
