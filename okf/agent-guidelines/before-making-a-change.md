---
type: Guideline
title: Before making a change
description: Preparation checklist before editing: task, requirement IDs, flow, upstream docs, extension strategy.
tags: [agents, workflow]
status: stable
generated: { by: process:agents-md-migration, at: 2026-11-03T13:00:00Z }
sources:
  - id: agents-md-v1
    resource: https://github.com/openflow-workspace/distribution/blob/d3fe65b488b6ed7a13c36a8b8079a0e1562e41cf/AGENTS.md
    title: AGENTS.md before migration to OKF
---

# Before making a change

1. Check the task, working tree, relevant instructions, and existing code. Preserve unrelated work.
2. Identify the requirement IDs affected by the change. For a new behavior, describe its acceptance criteria; update the requirements when appropriate.
3. Follow the complete affected flow: source API, extraction, Bronze, Silver, Gold, permissions, and dashboard when relevant.
4. Check official upstream documentation against the pinned version. Do not infer release support from the latest development branch.
5. Prefer configuration, supported extensions, and small adapters. A core patch needs a reason, a pinned base, and an update/removal strategy.
