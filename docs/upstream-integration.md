# Upstream integration map

This map records findings from the local upstream research collection. Default branches are reference material; they do not form a validated Openflow release. Check the sources at the release selected for an implementation.

## Local reference collection

The workspace contains 276 publicly listed projects from `bmi/opendesk` on openCode, including 18 projects reported as empty by the API, plus additional upstream references for Discourse, Frappe/ERPNext, and Superset. These remain independent repositories excluded from the Openflow Git repository. Local inventory files are research artifacts, not a release lockfile.

Most references are shallow clones. The openDesk deployment clone uses partial-clone filtering. Submodules and LFS payloads are not fully downloaded. Git LFS was not installed during collection; the ClamAV database mirror has pointer files. The two CryptPad checkouts have a case-insensitive filesystem collision between `FUNDING.json` and `funding.json`; their Git objects preserve both originals and separate local copies were retained under `.setup/case-collisions/`.

Projects with `deletion_scheduled` in their path and archived projects are historical references. Start with current paths when both exist. A source mirror is not evidence of downstream modifications.

## Nextcloud image and configuration

- [ZenDiS Nextcloud image](https://gitlab.opencode.de/bmi/opendesk/components/platform-development/images/opendesk-nextcloud): its `Dockerfile` builds the AIO image. `src/files/apps.yaml` selects app versions and `src/files/flavor.yaml` defines app combinations.
- Its `src/scripts/build/download_nextcloud_and_apps.py` downloads Nextcloud/apps and implements a version-specific patch mechanism. A patch mechanism alone does not prove that a given release applies patches. Enterprise downloads have separate credential handling.
- [Nextcloud chart](https://gitlab.opencode.de/bmi/opendesk/components/platform-development/charts/opendesk-nextcloud): the management subchart handles installation/configuration jobs.
- [openDesk deployment](https://gitlab.opencode.de/bmi/opendesk/deployment/opendesk): `helmfile/apps/nextcloud/values-nextcloud-management.yaml.gotmpl` configures LDAP, OIDC, and central navigation. The reviewed configuration uses the internal endpoint `http://ums-portal-server/portal/navigation.json`.

## Navigation and application extensions

- [Nextcloud integration_swp mirror](https://gitlab.opencode.de/bmi/opendesk/component-code/file/nextcloud/app_integration_swp): `lib/Service/MenuService.php`, `src/centralMenu.js`, and `src/components/CentralMenu.vue` illustrate the central-navigation contract and UI.
- [OpenProject openDesk plugin](https://gitlab.opencode.de/bmi/opendesk/component-code/project-management/openproject/opendesk-plugin) and [bootstrap image](https://gitlab.opencode.de/bmi/opendesk/components/platform-development/images/opendesk-openproject-bootstrap) illustrate application-specific integration and configuration.
- [Nextcloud OpenProject integration](https://github.com/nextcloud/integration_openproject) provides the Nextcloud side of the application connection. A menu link and a business/file integration are different features.

## Additional applications

The reviewed central openDesk files did not show a completed Discourse integration. The intended approach is a separate deployment, Keycloak client, portal entry, and dedicated navigation/business integration where needed.

- Additional Keycloak clients/scopes are configurable through `functional.authentication.oidc.clients` and `clientScopes` in the reviewed openDesk `functional.yaml.gotmpl`.
- Additional portal data can use `functional.portal.custom.extraDataFiles`; examples are in the [openDesk Nubus image](https://gitlab.opencode.de/bmi/opendesk/components/platform-development/images/opendesk-nubus), under `udm/udm-data-loader/`.
- Arbitrary Helm Values overrides can use `customization.release` file references. openDesk documents this powerful customization mechanism as outside its standard support scope.
- [Discourse](https://github.com/discourse/discourse) includes its OIDC plugin in the reviewed source. The [historical standalone plugin](https://github.com/discourse/discourse-openid-connect) points to this bundled implementation.
- [Frappe](https://github.com/frappe/frappe) supports custom apps and hooks; [ERPNext](https://github.com/frappe/erpnext), [Helm configuration](https://github.com/frappe/helm), and [container recipes](https://github.com/frappe/frappe_docker) are reference sources for that module.
- [Superset](https://github.com/apache/superset) includes a Keycloak example in the reviewed source at `docs/admin_docs/security/oauth.mdx`. Verify its extension points against the chosen release.

## Data platform references

The selected orchestration component is [Apache Airflow](https://github.com/apache/airflow). The intended analytical stack uses [pg_ducklake](https://github.com/relytcloud/pg_ducklake), [DuckLake](https://github.com/duckdb/ducklake), PostgreSQL, and S3-compatible storage. These references do not establish a tested compatibility combination. The requirements distinguish PostgreSQL's pg_ducklake extension from DuckDB's DuckLake extension using a PostgreSQL catalog.

The initial data milestone must demonstrate extraction, transformations, query access, authorization, dashboards, retries, and recovery together before any production-readiness claim.
