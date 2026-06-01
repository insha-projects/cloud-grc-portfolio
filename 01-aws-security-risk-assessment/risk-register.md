# AWS Security Risk Register

| Risk ID | Risk Description | Affected Asset | Likelihood | Impact | Risk Level | Existing Control | Recommendation |
|---|---|---|---|---|---|---|---|
| R-001 | Root account compromise could allow full control of the AWS account. | Root User | Low | Critical | High | MFA enabled for root user | Use root only for account-level tasks and monitor root sign-in activity |
| R-002 | Excessive administrative permissions could allow unauthorized or accidental changes to AWS resources. | CloudGRC-Admins | Medium | High | High | Separate admin group created and MFA enabled for admin user | Limit admin access to required users only and review permissions periodically |
| R-003 | Broad developer permissions may exceed job responsibilities. | CloudGRC-Developers | Medium | High | High | Developer group created separately from admin group | Replace broad PowerUserAccess with task-specific least privilege policies |
| R-004 | Lack of MFA on IAM users could increase the risk of unauthorized account access. | IAM Users | Medium | High | High | MFA enabled for cloud-grc-admin | Enforce MFA for all IAM users with console access |
| R-005 | Public S3 bucket access could expose stored data. | S3 Bucket | Low | High | Medium | S3 Block Public Access enabled | Keep public access blocked and review bucket policies regularly |
| R-006 | Misconfigured S3 encryption settings could expose data at rest. | S3 Bucket | Low | Medium | Medium | Default SSE-S3 encryption enabled | Maintain default encryption and avoid storing sensitive data in lab environments |
| R-007 | Limited logging visibility could reduce the ability to investigate security events. | CloudTrail Event History | Medium | Medium | Medium | CloudTrail Event History reviewed | Consider configuring a dedicated CloudTrail trail with centralized log storage in a future phase |
| R-008 | Unexpected AWS charges could occur if paid resources are created unintentionally. | AWS Account | Medium | Medium | Medium | AWS Budget alert created | Review billing dashboard regularly and avoid paid resources unless required |
| R-009 | Test users may become unmanaged if not reviewed or removed after testing. | grc-readonly-user, grc-developer-user | Medium | Medium | Medium | Test users created for lab documentation only | Review and remove unused test users after project completion |