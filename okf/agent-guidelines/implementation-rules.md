---
type: Guideline
title: Implementation rules
description: Rules for PR scope, reproducibility, data tasks, secrets, permissions and technology choices.
tags: [agents, implementation, security]
status: stable
generated: { by: process:agents-md-migration, at: 2026-11-03T13:00:00Z }
sources:
  - id: agents-md-v1
    resource: https://github.com/openflow-workspace/distribution/blob/d3fe65b488b6ed7a13c36a8b8079a0e1562e41cf/AGENTS.md
    title: AGENTS.md before migration to OKF
---

# Implementation rules

- Keep one coherent problem per PR. Separate unrelated cleanup.
- Keep the default stack reproducible and modules independently selectable.
- Version sources, schemas, transformations, metrics, and Superset assets together in a process package.
- Make data tasks retry-safe and interval-aware. Publish complete outputs before advancing extraction checkpoints. Never send bulk data through Airflow XCom.
- Use synthetic examples. Store secrets through runtime secret references, never in DAGs, SQL, configuration examples, or logs.
- Treat authentication, business permissions, and analytical data access as distinct controls. Never assume source application permissions automatically apply to the lakehouse.
- Do not edit operational application databases to implement analytical transformations.
- Record unresolved compatibility or design questions explicitly. Do not silently substitute a different technology for an agreed component.
