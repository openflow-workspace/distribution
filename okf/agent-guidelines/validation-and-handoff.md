---
type: Guideline
title: Validation and handoff
description: Required checks, handoff report contents and limits on pushing or publishing.
tags: [agents, validation, handoff]
status: stable
generated: { by: process:agents-md-migration, at: 2026-11-03T13:00:00Z }
sources:
  - id: agents-md-v1
    resource: https://github.com/openflow-workspace/distribution/blob/d3fe65b488b6ed7a13c36a8b8079a0e1562e41cf/AGENTS.md
    title: AGENTS.md before migration to OKF
---

# Validation and handoff

Run checks relevant to the changed files and behavior. Do not invent commands for tooling that does not exist. Documentation-only PRs should verify local links, language, and consistency. Runtime PRs should include meaningful tests for their acceptance criteria and relevant failure paths.

Before handing off, inspect the diff and report:

- The concrete behavior or documentation changed.
- Relevant requirement IDs and compatibility assumptions.
- The exact validation performed and its results.
- Anything not run, unavailable, or still open.

Do not push, merge, deploy, contact maintainers, or publish on a contributor's behalf unless their task authorizes it. Human contributors remain responsible for reviewing agent-generated changes and the PR they submit.
