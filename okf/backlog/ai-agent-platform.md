---
type: Backlog Item
title: "Epic: AI agent platform acting on behalf of the logged-in user"
description: Integrate an AI agent platform that performs tasks on other openDesk services in the name of the logged-in user, preferably via MCP.
tags: [ai, agents, mcp, epic]
status: draft
generated: { by: process:issue-migration, at: 2026-11-03T13:00:00Z }
sources:
  - id: issue-3
    resource: https://github.com/openflow-workspace/distribution/issues/3
    title: "Epic: AI agent platform acting on behalf of the logged-in user (via MCP) (closed, moved to OKF)"
---

# Goal

Integrate an AI agent platform into openDesk that performs tasks on the other services (for example search) **in the name of the logged-in user**, preferably via MCP.

# Building blocks

Built incrementally; scope is intentionally open.

- [Delegated user identity](/backlog/ai-agent-delegated-identity.md)
- [MCP access to services](/backlog/ai-agent-mcp-access.md)
- [RAG foundation](/backlog/ai-agent-rag.md)
- [AI-capable service interfaces](/backlog/ai-agent-ai-capable-apis.md)

# Notes

- No requirement ID is assigned yet; REQUIREMENTS.md does not currently cover this item.
- Related existing requirement: OF-003 (shared login through the openDesk identity/portal stack).
