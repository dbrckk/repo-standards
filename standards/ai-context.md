# AI context standard

Every active repository should expose a compact machine-readable context layer under `.ai/`.

Recommended files:
- `.ai/repo-map.md`: generated compact representation of relevant source/configuration files.
- `.ai/project-state.md`: concise current status, blockers, next priority, and last verification.
- `.ai/repo-health.md`: automated structural/quality audit.

Agents should read these files before broad repository exploration.

The generated repo map must exclude vendor dependencies, build outputs, caches, large assets, binaries, generated code when practical, and the `.ai/` directory itself.
