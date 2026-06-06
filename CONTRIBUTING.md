# Contributing

## Workflow

1. Create a short-lived branch from `main` using `feature/*`, `bugfix/*`, or `hotfix/*`.
2. Keep the change scoped to one objective.
3. Use Conventional Commits such as `docs: update repo standards` or `chore: standardize gitignore baseline`.
4. Open a Pull Request with:
   - a short summary
   - related issue or context
   - testing or validation performed

## Guardrails

- Do not commit directly to `main`.
- Do not commit secrets, credentials, or environment files with real values.
- Update documentation when behavior or workflow changes.

## Validation

Before opening a Pull Request:

- review the diff for scope
- confirm no secrets are included
- ensure documentation changes are accurate