# Repo Standards

These are not strict rules for every repo.

They are the habits I keep coming back to because they help me work well with AI without turning the codebase into chaos.

## What I Care About

- clear scope before broad implementation
- small enough changes that I can still review them properly
- enough documentation to preserve context
- enough validation to trust the result
- not letting AI quietly widen the problem

## Branching

I usually prefer:

- `main` as the stable branch
- short-lived feature or fix branches
- small, focused changes

I do not care about policing branch names for the sake of it. I care that the branch represents one clear piece of work.

## Commits

I generally use Conventional Commits because they keep history readable:

```text
feat: add cluster bootstrap check
fix: handle missing workload identity binding
docs: update deployment notes
```

If I drift from that occasionally, it is not the end of the world. The point is clarity, not ceremony.

## Reviews

My review standard is simple:

- can I understand the change quickly
- is the scope still what I intended
- did AI make hidden decisions for me
- do I have enough validation to trust it

For infra and platform work, I slow down more here than I do for normal app code.

## Docs

I like having a few predictable files:

- `docs/project-spec.md`
- `docs/architecture.md`
- `docs/ai-rules.md`
- `docs/tasks.md`

Not every repo needs all of them to be fully developed on day one.

I just want enough written down so the next AI pass does not start from nothing.

## Scripts And CI

I prefer to keep things as simple as possible.

Usually that means:

- use scripts when scripts are enough
- add GitLab CI only when deploy/test automation is genuinely useful
- keep host-specific files thin

I do not want CI to become theater.

## Riskier Work

I naturally review more carefully when a change touches:

- infrastructure
- CI/CD
- auth
- secrets
- migrations
- deploy or release flows

That does not mean “never let AI touch it.”

It means I want clearer scope, better review, and better validation.

## Practical Definition of Done

For me, a task is usually done when:

- the change does what I wanted
- the diff is understandable
- the validation is good enough for the risk
- the docs are updated if they need to be

That is enough.
