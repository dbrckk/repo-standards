# Testing standard

A repository should expose an obvious validation path.

Preferred order:
1. Fast syntax/static checks.
2. Unit tests.
3. Integration tests when applicable.
4. Build/package validation.
5. Release-specific validation when applicable.

Projects should document the canonical commands in README.md or `.ai/project-state.md`.

Agents must not claim validation succeeded when a command was not actually run.
