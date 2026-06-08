# Engineering System

This repo is a snapshot of how I like to work with AI when building infrastructure, platform tooling, and small internal apps.

It is not meant to be a heavy process framework. It is a lightweight working system that helps me stay fast without losing control of scope, architecture, and risk.

## Core Idea

I use AI as a planning and implementation partner.

I still own:

- what problem I am solving
- what trade-offs I accept
- what I merge
- what I deploy

## What I Optimize For

- fast iteration
- clear scope
- visible reasoning
- small diffs
- enough documentation to avoid rethinking the same decisions
- a workflow that works on GitHub and GitLab

## What This Repo Contains

1. [`AI-RULES.md`](AI-RULES.md)
   My default way of working with AI.
2. [`PROJECT-PROFILES.md`](PROJECT-PROFILES.md)
   The repo shapes I use most often.
3. [`repo-standards.md`](repo-standards.md)
   Shared habits I prefer across repos.
4. Companion template
   A starter repo with the docs and structure I usually want.

## Default Repo Shape

I usually want a repo to look roughly like this:

```text
project-root/
|-- config/
|-- docs/
|   |-- ai-rules.md
|   |-- architecture.md
|   |-- project-spec.md
|   `-- tasks.md
|-- infra/
|-- scripts/
|-- src/
|-- tests/
|-- README.md
`-- .gitignore
```

Not every repo needs every folder. The point is to have a predictable place for context, decisions, and execution notes.

## How I Usually Work

My default loop is:

```text
frame -> plan -> build -> review -> validate
```

For larger or riskier work, I lean more on docs and review.

For smaller work, I keep it light.

## GitHub And GitLab

I work across both, but not in the same way.

- GitHub repos are often script-first
- GitLab repos sometimes need deploy and test pipelines

So I do not want the system to assume every repo needs CI/CD from day one.

## AI Control Surfaces

These are the files I rely on most when using AI:

- `docs/project-spec.md`
- `docs/architecture.md`
- `docs/ai-rules.md`
- `docs/tasks.md`

I do not need all of them to be perfect before starting. I just want enough written down so the AI and I are working against the same boundaries.

## Companion Template

Use the companion template when starting a new repo:

1. Create from the template.
2. Pick the profile that feels closest.
3. Fill only the docs that are useful for the project.
4. Keep or remove folders based on actual need.
5. Add scripts people can run after cloning if that is enough.
6. Add or keep GitLab CI only when the project really needs deploy/test automation.

## What This Is Not

This is not:

- a strict methodology
- a compliance framework
- a generic enterprise standard
- a claim that every repo needs the same amount of process

It is just the working system I prefer.
