# Security standard

- Never commit secrets, private keys, production credentials, access tokens, or real .env files.
- Keep dependencies and CI actions pinned to explicit immutable SHAs where practical.
- Use least-privilege GitHub Actions permissions.
- Treat untrusted pull-request content as untrusted input.
- Avoid executing generated or repository-provided code with elevated permissions.
- Keep generated AI context free of secrets and large binary content.

## AI security signals

When `.ai/security-signals.json` exists:

- Treat it as heuristic evidence, not proof of compromise.
- Never reproduce a suspected secret value in generated context, comments, logs, or chat.
- Inspect the referenced file and line only when security work requires it.
- Distinguish source findings from `test_fixture_candidate` findings.
- High-severity signals should be verified before release-sensitive work.
- Low/medium test-fixture signals should not block work unless inspection shows a real credential.

The repository standards scanner records only category, path, line, context, and severity. It intentionally never stores the matched value.
