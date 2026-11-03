---
type: Backlog Item
title: "AI agents: act in the name of the logged-in user"
description: Agent actions on openDesk services run with the identity and permissions of the logged-in user.
tags: [ai, agents, identity]
status: draft
generated: { by: process:issue-migration, at: 2026-11-03T13:00:00Z }
sources:
  - id: issue-4
    resource: https://github.com/openflow-workspace/distribution/issues/4
    title: "AI agents: act on other services in the name of the logged-in user (identity/delegation) (closed, moved to OKF)"
---

Part of [the AI agent platform epic](/backlog/ai-agent-platform.md).

# Goal

Agent actions on openDesk services must be executed with the identity and permissions of the logged-in user.

# Open points

- Delegation mechanism (for example token exchange via the IdP): to be decided.
- Permission boundaries and auditability.
