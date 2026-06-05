# Standards

## Purpose

This document defines the engineering practices used across the project. The goal is to maintain code quality, predictable releases, fast onboarding, and support a trunk-based development workflow.

## Operating Model

These standards assume an AI-assisted workflow with clear human ownership:

* AI assists implementation and review speed.
* Engineers own architecture, risk decisions, and final approval.
* Work should be task-scoped and constraint-driven.

## AI Guardrails

For any AI-assisted task:

* Require a plan before implementation.
* Define explicit allowed and disallowed change scope.
* Review every generated diff before merge.
* Do not allow autonomous infrastructure, CI/CD, or architecture redesign actions.

## Terminology

* This document uses Pull Request (PR) as the standard term.
* In GitLab, PR maps to Merge Request (MR).

---

# Branching Strategy

## Overview

This project follows Trunk-Based Development (TBD).

### Branches

* `main` – Production-ready code
* `feature/*` – New features
* `bugfix/*` – Defect fixes
* `hotfix/*` – Critical production fixes

Examples:

```text
feature/project-onboarding-api
feature/gitlab-provisioning
bugfix/database-timeout
hotfix/authentication-failure
```

## Rules

* Direct commits to `main` are prohibited.
* All changes must be submitted through a Pull Request (PR).
* Feature branches should be short-lived (typically less than 2 days).
* Keep changes focused on a single issue or feature.
* Rebase frequently to stay current with `main`.
* Avoid batching unrelated changes in one branch.

---

# Commit Message Convention

This project uses Conventional Commits.

## Format

```text
<type>: <short description>
```

Examples:

```text
feat: add project creation API
feat: implement GitLab repository provisioning
fix: resolve namespace validation error
docs: update onboarding workflow
refactor: simplify database provisioning service
test: add integration tests for project creation
chore: update dependencies
```

## Allowed Types

| Type     | Purpose                    |
| -------- | -------------------------- |
| feat     | New functionality          |
| fix      | Bug fixes                  |
| docs     | Documentation              |
| refactor | Internal code improvements |
| test     | Testing                    |
| chore    | Maintenance tasks          |
| ci       | CI/CD changes              |

## Guidelines

* Use present tense.
* Keep subject concise.
* Keep the first line under 72 characters.
* Avoid generic messages such as:

  * update
  * fix stuff
  * changes

---

# Code Review Expectations

## Objectives

Code review exists to:

* Improve code quality
* Share knowledge
* Identify defects early
* Ensure consistency

## Reviewer Checklist

Reviewers should verify:

### Functionality

* Does the code solve the intended problem?
* Are edge cases considered?

### Maintainability

* Is the code easy to understand?
* Is duplication minimized?

### Security

* Are secrets excluded?
* Is input validation implemented?

### Testing

* Are tests included where appropriate?
* Do tests cover critical paths?

### Documentation

* Has documentation been updated if required?

## Review Standards

* Review the code, not the author.
* Provide constructive feedback.
* Explain reasoning behind requested changes.
* Approve only when comfortable supporting the code in production.

---

# Pull Request Workflow

## Development Process

```text
Issue
  ↓
Feature Branch
  ↓
Development
  ↓
Commit
  ↓
Pull Request
  ↓
Code Review
  ↓
Merge
  ↓
Deploy Staging
  ↓
UAT
  ↓
Production Release
```

## Creating a Pull Request

Every PR should include:

### Summary

What was implemented?

### Related Issue

Reference the associated issue.

Example:

```text
Closes #42
```

### Testing Performed

Describe:

* Unit tests
* Integration tests
* Manual validation

### Screenshots

Include UI screenshots when applicable.

## PR Size Guidelines

Preferred:

* Less than 500 lines changed
* One objective per PR

Avoid:

* Large multi-feature PRs
* Mixing refactoring with new functionality

## Merge Requirements

Before merge:

* CI pipeline passes
* Review completed
* Documentation updated if necessary
* No unresolved comments
* Rollback path is clear for high-risk changes

---

# Deployment Workflow

## Review Environment

Every Pull Request may deploy to a temporary review environment.

Purpose:

* Functional validation
* UI review
* Early testing

## Staging

After merge to `main`:

```text
main
  ↓
Deploy Staging
```

Staging should closely match production.

## Production

Production deployment requires:

* Successful staging validation
* UAT completion
* Approval

Release process:

```text
Build Artifact
  ↓
Deploy Staging
  ↓
UAT
  ↓
Create Release Tag
  ↓
Deploy Production
```

## Rollback

Rollback should redeploy the previous known-good artifact.

Do not rebuild old code for rollback.

Rollback procedure should be documented and tested for critical systems.

Example:

```text
v1.0.5
↓
Rollback
↓
v1.0.4
```

---

# Definition of Done

A task is considered complete when:

* Code is implemented
* Tests pass
* Code review completed
* Documentation updated
* CI pipeline successful
* Ready for deployment
* Scope boundaries were respected
