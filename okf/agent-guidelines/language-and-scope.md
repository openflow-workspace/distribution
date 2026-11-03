---
type: Guideline
title: Language and scope
description: Authoring language and repository boundaries versus upstream checkouts.
tags: [agents, language, scope]
status: stable
generated: { by: process:agents-md-migration, at: 2026-11-03T13:00:00Z }
sources:
  - id: agents-md-v1
    resource: https://github.com/openflow-workspace/distribution/blob/d3fe65b488b6ed7a13c36a8b8079a0e1562e41cf/AGENTS.md
    title: AGENTS.md before migration to OKF
---

# Language and scope

- Write all Openflow-owned documentation, code, comments, examples, issue templates, and PR content in English.
- Preserve exact upstream names, paths, identifiers, licenses, attribution, and source data. Do not translate or mass-edit third-party checkouts to enforce the English rule. Multilingual product support remains possible; English is the project authoring language.
- The adjacent `component-code`, `components`, `deployment`, `upstream`, `tooling`, and other downloaded repositories are independent upstream reference checkouts. They are excluded from this repository. Their own agent and contribution instructions apply within them.
- Do not add nested upstream repositories, large datasets, build outputs, credentials, or private company configuration to a commit.
