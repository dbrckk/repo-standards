# Security standard

- Never commit secrets, private keys, production credentials, access tokens, or real .env files.
- Keep dependencies and CI actions pinned to explicit major versions or immutable SHAs where practical.
- Use least-privilege GitHub Actions permissions.
- Treat untrusted pull-request content as untrusted input.
- Avoid executing generated or repository-provided code with elevated permissions.
- Keep generated AI context free of secrets and large binary content.
