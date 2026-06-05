# Engineering System

This repository defines a reusable engineering system for software and infrastructure projects.

The objective is simple: keep delivery speed high without sacrificing architectural quality, ownership, or learning.

## Core Position

AI is an implementation accelerator, not an autonomous owner.

Decision ownership remains with the engineer.

## Principles

- AI assists, human decides.
- Plan before implementation.
- One scoped task at a time.
- Review every diff before merge.
- Markdown docs are the source of truth.
- No autonomous infrastructure actions.
- No architecture redesign without explicit approval.
- Stable process over tool churn.

## Standard Project Shape

Use a consistent repository structure so planning, execution, and onboarding stay predictable.

```text
project-root/
|
|-- docs/
|   |-- project-spec.md
|   |-- architecture.md
|   `-- tasks.md
|
|-- src/
|-- infra/
|-- scripts/
|-- README.md
`-- .gitignore
```

## Delivery Loop

Every change follows this sequence:

```text
Plan -> Implement -> Review diff -> Validate architecture -> Continue
```

This is mandatory for high-blast-radius areas, including infrastructure, CI/CD, and platform automation.

## AI Task Framing

Prefer constrained prompts over open-ended requests.

```text
Implement task 2 only.

Allowed:
- modify Helm manifests

Not allowed:
- CI/CD changes
- Terraform changes
- new dependencies

Explain plan before coding.
Wait for approval.
```

## Standards Reference

Process standards for branching, commits, pull requests, reviews, deployment, and release quality gates are defined in [repo-standards.md](repo-standards.md).

## Companion Template

Use the companion template repository to start new projects with this system pre-wired:

- GitHub: https://github.com/chinmaymjog/project-template

Recommended usage:

1. Create a new repository from the template.
2. Fill `docs/project-spec.md`, `docs/architecture.md`, and `docs/tasks.md`.
3. Apply the standards defined in this repository.