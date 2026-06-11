# Access Control Matrix

## Purpose

The access control matrix defines which user groups receive access to AWS and what permission level is assigned to each group.

This supports least privilege access, access review readiness, and clear documentation of cloud access decisions.

## User Group and Permission Mapping

| User Group | Business Role | AWS Permission Set | Access Level | Justification |
|---|---|---|---|---|
| Cloud Administrators | Cloud platform administrators | AdministratorAccess | Full administrative access | Required to manage IAM Identity Center, permission sets, account access, and cloud configuration |
| Cloud Developers | Application or cloud engineers | PowerUserAccess | Resource management without full IAM administration | Allows developers to create and manage AWS resources while limiting identity and access management privileges |
| Cloud Security | Security analysts or cloud security team | SecurityAudit | Security visibility and audit access | Allows security users to review security configurations, IAM settings, logs, and compliance-related information |
| Cloud Auditors | Internal auditors or compliance reviewers | ReadOnlyAccess | Read-only visibility | Allows auditors to review AWS configurations and evidence without making changes |

## Sample User Assignments

| Sample User | Assigned Group | Intended AWS Access |
|---|---|---|
| Alex Admin | Cloud Administrators | Administrator-level AWS access |
| Dev User | Cloud Developers | Developer-level AWS access |
| Sec Analyst | Cloud Security | Security audit access |
| Audit Reviewer | Cloud Auditors | Read-only audit access |

## Access Governance Notes

Access is assigned based on job function rather than individual preference. This supports role-based access control and reduces the risk of excessive permissions.

Privileged access should be reviewed regularly to confirm that users still require the assigned level of access.

In a production environment, access requests should be approved by the appropriate manager or system owner before assignment.
