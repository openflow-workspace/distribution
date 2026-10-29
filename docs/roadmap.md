# Roadmap

This roadmap describes planned milestones. It is not a release announcement or a completion checklist.

## M0: Public project foundation

Publish an English project overview, requirements, contribution guide, agent instructions, and public organization profile. Identify open architecture and licensing decisions. Keep proposed features clearly distinguished from implemented behavior.

Relevant requirements: OF-005, OF-006.

## M1: Reproducible collaboration baseline

Select a supported openDesk release, record its component/image/chart pins, and define modular downstream configuration. Establish a repeatable evaluation deployment and upgrade checks. Settle the license policy for Openflow-owned implementation work before accepting substantive executable contributions.

Relevant requirements: OF-001, OF-004, OPS-001, OPS-002, OPS-003, OPS-007.

## M2: Application entry points

Add selectable Discourse, ERPNext, and Superset deployments, shared login, explicit role/account lifecycle mappings, and portal entries. Verify login, navigation, least-privileged access, and account disablement. Add stable cross-application links before considering automated business-object synchronization.

Relevant requirements: OF-002, OF-003, IG-001, IG-005, IG-006.

## M3: Data platform compatibility baseline

Prove a pinned Airflow/PostgreSQL/pg_ducklake/S3/Superset combination. Define catalog ownership, storage layout, secrets, query connectivity, access enforcement, and restore procedure. Record measured behavior and unsupported combinations.

Relevant requirements: DATA-001 through DATA-005, AF-001, AF-006, IG-002 through IG-004, OPS-004 through OPS-006.

## M4: Sales and receivables vertical slice

Deliver PP-001 from synthetic ERPNext-compatible input through Bronze, Silver, Gold, and supplied Superset dashboards. Implement and run all first-vertical-slice acceptance criteria in the requirements, including retries, failed quality gates, backfills, tenant isolation, and recovery.

An agreed metric dictionary and reproducible fixtures are prerequisites. Start with invoice amounts and outstanding balances; do not advertise profit or recognized revenue without their required rules and inputs.

Relevant requirements: PP-001, BR-001 through BR-004, SI-001 through SI-005, GO-001 through GO-004, AF-002 through AF-008, BI-001 through BI-006.

## M5: Additional process packages and first suite release

Extend the proven packaging model to purchasing/inventory and project delivery. Add real source connectors for selected versions, release manifests, upgrade/migration guidance, and end-to-end application/data checks. Publish installation and operational expectations only when validated.

Relevant requirements: PP-002, PP-003, OPS-001 through OPS-007.

## Later candidates

Optional aggregate collaboration/community analytics, additional ERP processes, narrowly scoped APIs/events between applications, and CDC where its operational cost is justified. These require their own scope and acceptance criteria rather than being implicit requirements of the first release.
