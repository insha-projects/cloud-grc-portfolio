# IAM User Inventory

| User ID | IAM User | Console Access | MFA Status | Group Membership | Purpose | Risk Rating |
|---|---|---|---|---|---|---|
| U-001 | cloud-grc-admin | Enabled | Enabled | CloudGRC-Admins | Daily administrative user for AWS lab activities | High |
| U-002 | grc-readonly-user | Disabled | Not applicable | CloudGRC-ReadOnly | Test user for read-only access governance review | Low |
| U-003 | grc-developer-user | Disabled | Not applicable | CloudGRC-Developers | Test user for developer access governance review | Medium |

## Notes

The `cloud-grc-admin` user has console access and MFA enabled. This user is used for daily lab administration instead of the AWS root user.

The `grc-readonly-user` and `grc-developer-user` accounts do not have console access enabled. Since they cannot sign in to the AWS Management Console, MFA is not applicable for these test users in this lab environment.

In a production environment, all users with console access should be required to use MFA.