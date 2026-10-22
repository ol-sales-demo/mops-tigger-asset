# AGENTS.md

This file defines guidelines and guardrails for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow these rules at all times when working in this repository.

### Protect Sensitive Data

- Do not read, log, print, or include secrets, API keys, tokens, credentials, or environment variable values in any file, commit, or output. Referencing variable names (e.g. `$DATABASE_URL`) is acceptable; writing their values is not.
- Do not commit `.env` files or any file containing plaintext credentials.
- Do not include personally identifiable information (PII) or customer data in code, comments, logs, or test fixtures.
- When adding new configuration, always reference secrets via environment variables — never hardcode values.

### Prevent Unauthorized Deployments

- Do not push directly to `main`, `master`, or any branch that triggers an automatic deploy to the Railway production environment.
- Do not trigger, modify, or bypass CI/CD pipelines, deployment workflows, or release processes without explicit human approval.
- Do not create or modify Railway configuration files (e.g. `railway.json`, `Procfile`) in a way that would alter the production runtime environment without explicit approval.
- Do not bump the package version or publish the package to any registry without explicit instruction.

### Avoid Destructive Operations

- Do not force-push (`git push --force`) to any branch.
- Do not delete branches, tags, or remote refs.
- Do not drop, truncate, or run irreversible migrations against any database or data store.
- Do not remove or overwrite dependency lockfiles without regenerating them correctly (run `npm install` to regenerate `package-lock.json`).
- Do not execute commands that are irreversible in production contexts (e.g. `heroku destroy`, `railway down`) without explicit approval.
- Prefer additive, reversible changes. When in doubt, open a pull request for human review rather than applying changes directly.
