# Application modules: status and open points

This page records what is known about additional application modules. It is a status note, not a completion checklist. Nothing here is implemented or verified in this repository. Requirement IDs are defined in [REQUIREMENTS.md](../REQUIREMENTS.md) under "Application modules".

## Discourse (DISC-001 to DISC-003)

Priority: first application integration.

Prepared outside this repository and not included here (offline-checked only):

- a configuration generator, a launcher example, and an adapter for Discourse settings;
- an openDesk overlay for Keycloak/OIDC and the portal.

Not yet done: real login, portal navigation, and operation in an openDesk environment; verification of access rights. For the upstream review of the integration approach, see [upstream-integration.md](upstream-integration.md).

## Kept notes (NOTE-001 to NOTE-004)

Prepared outside this repository and not included here:

- an optional module with its own SQLite storage, an example configuration, a disabled OIDC client, and settings for portal, ingress, and WebSockets.

Not yet done: image selection, deployment, and the suitability check (license, maintenance, OIDC/SSO, sharing model). The sharing requirement (NOTE-003) comes from the original request; the preparation described above does not mention sharing.

## Ticketing (TKT-001, TKT-002)

Documented for later. Two workflow types are intended: internal IT support and external requests from customers, partners, or suppliers. The module can be switched off. Products are to be compared later against both workflow types; no product is selected.

## Development platform (DEV-001)

Documented for later. Gitea and Forgejo are candidates for self-hosting. Codeberg is noted separately as a hosted option for public project collaboration.
