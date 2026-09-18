# New project bootstrap policy

Every new `dbrckk` repository must adopt the shared repository-intelligence stack from its first usable commit.

Required files:

- `AGENTS.md` from `templates/AGENTS.md`
- `.repo-standards.yml` from `templates/repo-standards.yml`
- `.github/workflows/ai-repo-map.yml` from `templates/adopt-standards.yml`
- `.ai/project-state.md` from `templates/project-state.md`

The workflow must follow `dbrckk/repo-standards@main` and the repository config must follow `dbrckk/repo-brain@main`.

The standard stack includes:

- incremental repository indexing;
- AST symbol routing;
- bounded hotsets and context packets;
- compact dependency graph shards;
- reverse dependency lookup;
- hash-based reuse;
- persistent session/project state;
- Mermaid architecture output for optional human inspection.

## Creation rule

When creating a repository, bootstrap these files before feature development begins.

Do not wait for the repository to become large. Small repositories should use the same structure so that context remains consistent as they grow.

## Existing active repositories

Repositories with pushes in the last 7 days should be checked for this bootstrap and upgraded to the current template when missing or stale.

## Empty repository exception

An empty GitHub repository without an initial commit may not accept Contents API writes. In that case, create the first commit, then apply the bootstrap immediately.
