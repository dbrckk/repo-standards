# Versioning standard

Stable consumers must reference a release branch such as `@v3`, not `@main`.

- `main` is the development line for the next standards version.
- A release branch such as `v3` is treated as immutable after promotion except for critical fixes.
- New standards are tested on one pilot repository before promotion.
- After successful pilot validation, create the next release branch and migrate consumers deliberately.
- Repository manifests must record both `ref` and `version`.

This prevents an experimental change in repo-standards from breaking every adopted repository at once.
