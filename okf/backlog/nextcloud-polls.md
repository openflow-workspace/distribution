---
type: Backlog Item
title: Include Nextcloud Polls plugin for appointment scheduling
description: Include the Nextcloud polls plugin in openDesk for finding dates.
tags: [opendesk, nextcloud, scheduling]
status: draft
generated: { by: process:issue-migration, at: 2026-11-03T13:00:00Z }
sources:
  - id: issue-2
    resource: https://github.com/openflow-workspace/distribution/issues/2
    title: "Include Nextcloud Polls plugin for scheduling appointments (closed, moved to OKF)"
---

# Goal

Include the Nextcloud `polls` plugin in openDesk for appointment scheduling (finding dates).

# Acceptance criteria

- [ ] Plugin is installed/enabled in the Nextcloud deployment of the distribution.
- [ ] Compatibility with the Nextcloud version used by openDesk verified.
- [ ] Usable by logged-in users for date polls.

# Notes

- Requirement was captured from a conversation; scope and details are to be refined incrementally.
- Nextcloud image and app selection upstream: see `docs/upstream-integration.md` (section "Nextcloud image and configuration").
- No requirement ID is assigned yet; REQUIREMENTS.md does not currently cover this item.
