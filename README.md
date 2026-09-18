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


## v4 context intelligence

The experimental v4 context layer adds:

- `.ai/architecture.json` for project type, descriptors, top-level modules and entrypoint candidates.
- `.ai/commands.json` for detected test/build/lint commands.
- `.ai/change-impact.md` for the latest changed files, affected areas and direct test candidates.

Recommended v4 reading order:

1. `.ai/project-state.md`
2. `.ai/change-impact.md`
3. `.ai/architecture.json`
4. `.ai/commands.json`
5. `.ai/repo-health.md`
6. `.ai/repo-map.md` only when needed


## v5 observability

The experimental v5 layer adds:

- `.ai/ci-status.md` for recent non-standards GitHub Actions results.
- `.ai/security-signals.json` for heuristic secret/risky-file locations without ever writing matched values.
- `.ai/dependency-map.json` for manifests, external dependencies, inferred imports, and internal roots.

Security findings include context and severity. Test fixtures are marked separately to reduce false-positive confusion.

Recommended v5 reading order:

1. `.ai/project-state.md`
2. `.ai/change-impact.md`
3. `.ai/architecture.json`
4. `.ai/dependency-map.json`
5. `.ai/commands.json`
6. `.ai/ci-status.md`
7. `.ai/security-signals.json`
8. `.ai/repo-health.md`
9. `.ai/index.md`
10. Relevant `.ai/maps/<area>.md`
11. `.ai/repo-map.md` only when required
