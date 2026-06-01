# AWS Asset Inventory

| Asset ID | AWS Service | Asset Name | Purpose | Data Sensitivity | Owner |
|---|---|---|---|---|---|
| A-001 | AWS Account | Insha Cloud GRC Lab | Personal AWS lab account for portfolio project | High | Cloud Admin |
| A-002 | IAM | Root User | Account owner identity with full administrative control | Critical | Cloud Admin |
| A-003 | IAM | cloud-grc-admin | Daily administrative user for lab activities | High | Cloud Admin |
| A-004 | IAM User Group | CloudGRC-Admins | Administrative access group | High | Cloud Admin |
| A-005 | IAM User Group | CloudGRC-ReadOnly | Read-only access group for governance demo | Medium | Cloud Admin |
| A-006 | IAM User Group | CloudGRC-Developers | Developer access group for governance demo | High | Cloud Admin |
| A-007 | IAM User | grc-readonly-user | Test user assigned to read-only access | Medium | Cloud Admin |
| A-008 | IAM User | grc-developer-user | Test user assigned to developer access | High | Cloud Admin |
| A-009 | Amazon S3 | cloud-grc-lab-insha-2026-001 | Sample cloud storage bucket | Low | Cloud Admin |
| A-010 | AWS Budgets | Zero-Spend-Cloud-GRC-Lab | Cost monitoring and budget alerting | Medium | Cloud Admin |
| A-011 | CloudTrail | Event History | Audit visibility for recent AWS account activity | Medium | Cloud Admin |