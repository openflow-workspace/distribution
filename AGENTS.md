# Working on Openflow with a coding agent

## Project context

Openflow is an opinionated enterprise suite distribution built around openDesk, with Discourse, ERPNext, Apache Superset, Apache Airflow, and a PostgreSQL/pg_ducklake/S3 data platform. Read `README.md`, `REQUIREMENTS.md`, and `CONTRIBUTING.md` before editing.

This repository is in the requirements and architecture stage. A component listed in the requirements is a target, not proof of a working integration. Do not claim a deployment, connector, dashboard, test, or release exists without checking its implementation.

## Language and scope

- Write all Openflow-owned documentation, code, comments, examples, issue templates, and PR content in English.
- Preserve exact upstream names, paths, identifiers, licenses, attribution, and source data. Do not translate or mass-edit third-party checkouts to enforce the English rule. Multilingual product support remains possible; English is the project authoring language.
- The adjacent `component-code`, `components`, `deployment`, `upstream`, `tooling`, and other downloaded repositories are independent upstream reference checkouts. They are excluded from this repository. Their own agent and contribution instructions apply within them.
- Do not add nested upstream repositories, large datasets, build outputs, credentials, or private company configuration to a commit.

## Before making a change

1. Check the task, working tree, relevant instructions, and existing code. Preserve unrelated work.
2. Identify the requirement IDs affected by the change. For a new behavior, describe its acceptance criteria; update the requirements when appropriate.
3. Follow the complete affected flow: source API, extraction, Bronze, Silver, Gold, permissions, and dashboard when relevant.
4. Check official upstream documentation against the pinned version. Do not infer release support from the latest development branch.
5. Prefer configuration, supported extensions, and small adapters. A core patch needs a reason, a pinned base, and an update/removal strategy.

## Implementation rules

- Keep one coherent problem per PR. Separate unrelated cleanup.
- Keep the default stack reproducible and modules independently selectable.
- Version sources, schemas, transformations, metrics, and Superset assets together in a process package.
- Make data tasks retry-safe and interval-aware. Publish complete outputs before advancing extraction checkpoints. Never send bulk data through Airflow XCom.
- Use synthetic examples. Store secrets through runtime secret references, never in DAGs, SQL, configuration examples, or logs.
- Treat authentication, business permissions, and analytical data access as distinct controls. Never assume source application permissions automatically apply to the lakehouse.
- Do not edit operational application databases to implement analytical transformations.
- Record unresolved compatibility or design questions explicitly. Do not silently substitute a different technology for an agreed component.

## Validation and handoff

Run checks relevant to the changed files and behavior. Do not invent commands for tooling that does not exist. Documentation-only PRs should verify local links, language, and consistency. Runtime PRs should include meaningful tests for their acceptance criteria and relevant failure paths.

Before handing off, inspect the diff and report:

- The concrete behavior or documentation changed.
- Relevant requirement IDs and compatibility assumptions.
- The exact validation performed and its results.
- Anything not run, unavailable, or still open.

Do not push, merge, deploy, contact maintainers, or publish on a contributor's behalf unless their task authorizes it. Human contributors remain responsible for reviewing agent-generated changes and the PR they submit.
