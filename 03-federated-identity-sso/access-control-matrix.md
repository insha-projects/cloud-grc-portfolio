# Access Control Matrix

## Purpose

The access control matrix defines which Okta group receives access to AWS and what AWS federated role is assigned.

This supports least privilege access, access review readiness, and clear documentation of cloud access decisions.

## Implemented Access Mapping

| Okta Group | Business Role | AWS Federated Role | AWS Permission Policy | Access Level | Justification |
|---|---|---|---|---|---|
| Cloud-Auditors | Internal auditors and compliance reviewers | Okta-ReadOnlyAudit-Role | ReadOnlyAccess | Read-only visibility | Allows auditors to review AWS resources and configurations without making changes |

## Additional Groups Created for Simulation

The following Okta groups were created to represent a broader enterprise access model:

| Okta Group | Intended Business Role | Intended Access Model |
|---|---|---|
| Cloud-Administrators | Cloud platform administrators | Administrative access for cloud management |
| Cloud-Developers | Application or cloud engineers | Developer access for managing cloud resources |
| Cloud-Security | Security analysts or cloud security team | Security review and monitoring access |
| Cloud-Auditors | Internal auditors or compliance reviewers | Read-only access for audit and evidence collection |

## Sample User Assignments

| Sample User | Assigned Group | Intended AWS Access |
|---|---|---|
| Alex Admin | Cloud-Administrators | Administrative cloud access |
| Dev User | Cloud-Developers | Developer-level cloud access |
| Sec Analyst | Cloud-Security | Security review access |
| Audit Reviewer | Cloud-Auditors | Read-only audit access |
| Insha Dosani | Cloud-Auditors | Active user used to validate Okta-to-AWS SAML federation |

## Access Governance Notes

Access is assigned based on job function rather than individual preference. This supports role-based access control and reduces the risk of excessive permissions.

For this lab, the Cloud-Auditors group was implemented and tested using a read-only AWS federated role.

Privileged access should be reviewed regularly to confirm that users still require the assigned level of access.

In a production environment, access requests should be approved by the appropriate manager or system owner before assignment.
