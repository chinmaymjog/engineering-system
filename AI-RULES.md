# AI Rules

This is my default way of working with AI.

It is intentionally lightweight.

## Core Rule

AI helps me think, plan, and build.

I keep control of scope, architecture, risk, and final decisions.

## What I Usually Give The AI

When I want good output, I usually make these things clear:

- what I am trying to do
- what files or areas are in scope
- what should stay untouched
- how much risk I am willing to take
- what kind of validation I want back

I do not force a rigid format every time, but the clearer I am, the better the result.

## My Default Modes

- `Explore`
  Read, trace, summarize, and suggest options.
- `Build`
  Make changes inside the scoped area.
- `High-Risk Build`
  Prepare changes for infra, CI, auth, secrets, migrations, or release flows, but slow down and review more carefully.

## When I Slow Down

I usually pause and review more carefully when the change touches:

- infrastructure
- CI/CD
- security-sensitive code
- auth
- secrets
- data migrations
- public interfaces
- deploy or release automation

## What I Expect Back

I want AI work to leave behind:

- a clear diff
- enough reasoning to understand the change
- validation notes or commands when relevant
- doc updates if the behavior or architecture changed

## Practical Rule

If the AI starts widening scope, making hidden decisions, or producing a messy diff, I narrow the task and try again.

That is usually better than trying to rescue a bad broad change.
