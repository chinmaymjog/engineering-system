# Contributing

Use this repository to evolve shared engineering standards and workflow guidance.

## Workflow

1. Create a short-lived branch from `main` using `feature/*`, `bugfix/*`, or `hotfix/*`.
2. Keep the change scoped to one objective.
3. Use Conventional Commits such as `docs: update repo standards` or `chore: standardize gitignore baseline`.
4. Validate the affected docs or standards before opening a Pull Request.
5. Open a Pull Request with a short summary, related context, and validation performed.

## Repo-Specific Guidance

- Keep guidance generic enough to apply across multiple project types.
- Update [repo-standards.md](/Users/chinmayjog/repos/personal/engineering-system/repo-standards.md) when branching, PR, or release expectations change.
- Prefer small, incremental improvements over large process rewrites.

## Guardrails

- Do not commit directly to `main`.
- Do not commit secrets, credentials, or environment files with real values.
- Do not change standards and examples in unrelated ways in the same PR.

## Validation

Before opening a Pull Request:

- review the diff for scope
- confirm no secrets are included
- ensure documentation changes are accurate

## Documentation Updates

- Update README usage notes when the recommended workflow changes.
- Keep examples and repository shape guidance aligned with the companion template repo.