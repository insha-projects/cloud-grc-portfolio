# IAM Group Permissions Review

| Group ID | IAM Group | Attached Policy | Permission Level | Purpose | Risk Rating | Review Notes |
|---|---|---|---|---|---|---|
| G-001 | CloudGRC-Admins | AdministratorAccess | Full administrative access | Administrative access for lab management | High | Appropriate for a personal lab admin user, but high risk in production |
| G-002 | CloudGRC-Developers | PowerUserAccess | Broad non-IAM administrative access | Developer access simulation | High | Broad permissions should be replaced with least-privilege task-based policies |
| G-003 | CloudGRC-ReadOnly | ReadOnlyAccess | Read-only access | Read-only review and audit-style access | Low | Supports least privilege for users who only need visibility |

## Permission Review Summary

The IAM group structure demonstrates role-based access separation by using separate groups for administrative, developer, and read-only access.

The `CloudGRC-Admins` group uses `AdministratorAccess`, which provides full administrative privileges. This is acceptable for a personal lab environment but would require strong justification, MFA enforcement, and periodic review in a production environment.

The `CloudGRC-Developers` group uses `PowerUserAccess`, which is broad and may provide more access than required for a typical developer role. This group should be refined using least-privilege permissions.

The `CloudGRC-ReadOnly` group uses `ReadOnlyAccess`, which aligns more closely with least-privilege access for audit, review, and visibility purposes.