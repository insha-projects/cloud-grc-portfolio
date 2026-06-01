# Security Controls Review

| Control Area | Control Implemented | Purpose | Status | Evidence |
|---|---|---|---|---|
| Account Security | Root MFA enabled | Reduces risk of unauthorized access to the AWS root account | Implemented | 01-root-mfa-enabled.png |
| Billing Governance | IAM billing access activated | Allows authorized IAM users to access billing information | Implemented | 02-iam-billing-access-enabled.png |
| Cost Monitoring | AWS budget alert created | Helps detect unexpected AWS spending | Implemented | 03-budget-alert-created.png |
| Privileged Access Management | Admin user group created | Separates daily administrative activity from root account use | Implemented | 04-admin-group-created.png |
| IAM User Management | IAM admin user created | Provides a dedicated user for daily lab administration | Implemented | 05-admin-user-created.png |
| Privileged Identity Protection | MFA enabled for IAM admin user | Protects privileged console access | Implemented | 06-admin-user-mfa-enabled.png |
| Root Account Avoidance | Admin user used for project work | Reduces routine use of the root account | Implemented | 07-admin-user-signed-in.png |
| Storage Security | S3 bucket created for lab assessment | Provides a sample cloud storage asset for security review | Implemented | 08-s3-bucket-created.png |
| S3 Public Access Protection | Block Public Access enabled | Reduces risk of accidental public exposure | Implemented | 09-s3-block-public-access.png |
| S3 Encryption | Default SSE-S3 encryption enabled | Protects stored objects at rest | Implemented | 10-s3-default-encryption.png |
| Access Segmentation | ReadOnly IAM group created | Demonstrates limited-access role design | Implemented | 11-readonly-group-created.png |
| Access Segmentation | Developer IAM group created | Demonstrates role-based access separation | Partially Implemented | 12-developer-group-created.png |
| IAM Test User Review | Test IAM users created | Demonstrates user-to-group access assignment | Implemented | 13-test-users-created.png |
| IAM Group Membership | ReadOnly user assigned to ReadOnly group | Confirms access assignment through group membership | Implemented | 14-user-group-membership.png |
| Audit Logging | CloudTrail Event History reviewed | Provides visibility into recent AWS management events | Implemented | 15-cloudtrail-event-history.png |
| Audit Evidence Review | CloudTrail event detail reviewed | Confirms specific AWS activity was logged | Implemented | 16-cloudtrail-event-detail.png |