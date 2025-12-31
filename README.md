# Cloud Project

## Product vision & scope
- Secure, compliant file management and sharing platform that supports individual, team, and enterprise use.
- Scope includes RBAC-based access control, large-file upload/download, version history, activity/audit visibility, and region-aware storage with encryption.

## Functional requirements
- End users: upload/download large files, organize into folders/spaces, search by name/metadata, generate public or time-bound share links, view/restore versions, desktop/mobile sync.
- Admins: manage users, roles/policies, quotas; configure regions; monitor usage.
- Auditors: read-only access to activity logs and reports.
- Authorization: RBAC as primary; support ABAC for advanced policies (e.g., data residency, sharing limits).
- Activity logs & audit trails captured for uploads/downloads/shares/admin actions.

## Non-functional requirements
- Availability ≥ 99.9% with defined SLAs for support and recovery.
- Disaster recovery with explicit RPO/RTO targets; backups and region-aware replication.
- Security: encryption in transit and at rest; hardened public links (time-bound/permissioned); compliance alignment with SOC 2 and HIPAA when regulated data is present.
- Performance: upload/download latency targets appropriate for large files; desktop/mobile sync optimized for bandwidth.
- Data residency: region-specific storage selection per policy.
- Cost awareness: track storage, bandwidth, and compute efficiency.

## Phase-1 architecture readiness
- RBAC/ABAC layer in front of storage services; scoped roles for end users, admins, auditors.
- Object storage per region with server-side encryption; signed URLs for time-bound sharing.
- Metadata/indexing service to power search, version history, and audit/event capture.
- Logging pipeline for activity/audit trails with read-only auditor access.
- Sync clients (desktop/mobile) leveraging the same APIs for upload/download and delta updates.
