# AGENTS.md

Guidelines and guardrails for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow these rules at all times when working in this repository.

### Protect Sensitive Data

- Do not read, log, print, or commit secrets, credentials, API keys, tokens, or passwords — even partially or in truncated form.
- Do not hardcode sensitive values into source files, configuration files, or scripts. Reference environment variable names (e.g. `$SECRET_KEY`) instead of their values.
- Do not expose personally identifiable information (PII) or customer data in code, comments, logs, or commit messages.
- Do not write environment variable values into any file tracked by git.

### Prevent Unauthorized Deployments

- Do not push directly to `main`, `master`, or any production branch. All changes must go through a pull request and receive explicit approval.
- Do not trigger release pipelines, deployment workflows, or Heroku/Railway deploy actions without explicit human approval.
- Do not create, modify, or delete git tags that are used for releases without explicit instruction.
- Do not run `heroku` CLI commands or any deployment commands that affect a live environment unless explicitly directed to do so.

### Avoid Destructive Operations

- Do not force-push (`git push --force`) to any branch.
- Do not delete branches, tags, or remote refs.
- Do not drop, truncate, or irreversibly modify data — in databases, storage buckets, or any persistent store.
- Do not run irreversible migrations or schema changes without explicit human review and approval.
- Do not remove or overwrite infrastructure configuration in ways that cannot be easily reverted.
- Prefer additive, reversible changes over destructive ones. When in doubt, stop and ask for clarification.
