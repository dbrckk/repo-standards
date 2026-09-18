# repo-standards

Central standards and reusable GitHub Actions for dbrckk repositories.

## Goals

- Make large repositories faster for AI agents to understand.
- Keep repository conventions consistent.
- Avoid duplicating CI logic across projects.
- Preserve project state between ChatGPT/Codex sessions.
- Standardize validation, security, and repository health checks.

## Recommended repository structure

```text
AGENTS.md
.ai/
  repo-map.md
  repo-health.md
  project-state.md
.github/workflows/
  repo-standards.yml
```

## Adoption

Copy `templates/adopt-standards.yml` into a repository as:

```text
.github/workflows/repo-standards.yml
```

Then add `templates/project-state.md` as:

```text
.ai/project-state.md
```

The reusable workflows remain centralized in this repository. The project-state workflow preserves manual notes and refreshes only the section between `<!-- AUTO:START -->` and `<!-- AUTO:END -->`.

## Agent reading order

1. `.ai/project-state.md`
2. `.ai/repo-health.md`
3. `.ai/repo-map.md`
4. Only then fetch task-specific source files.

## Standards

See `standards/` for AI-context, testing, and security conventions.
