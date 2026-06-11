# Testing and Validation

## Purpose

Testing and validation confirm that users receive the correct AWS access based on their assigned group and permission set.

The goal is to verify that access is role-based, least privilege is applied, and users do not receive unnecessary permissions.

## Test Scenarios

| Test Case | User Group | Expected Result | Status |
|---|---|---|---|
| Admin user login | Cloud Administrators | User can access AWS with administrator permissions | Pending |
| Developer user login | Cloud Developers | User can manage AWS resources but should not have full IAM administration access | Pending |
| Security user login | Cloud Security | User can view security-related AWS configurations and audit information | Pending |
| Auditor user login | Cloud Auditors | User can view AWS resources but cannot make changes | Pending |

## Validation Checks

The following checks will be performed during implementation:

- Confirm users can access the AWS access portal through single sign-on.
- Confirm each user is assigned to the correct group.
- Confirm each group is mapped to the correct permission set.
- Confirm users receive access only to the intended AWS account.
- Confirm lower-privilege users cannot perform administrative actions.
- Capture screenshots as audit evidence.

## Evidence to Capture

Screenshots should be collected for:

- Okta user creation
- Okta group creation
- AWS IAM Identity Center configuration
- Permission set creation
- User/group assignment
- AWS access portal login
- Successful access test
- Failed or restricted access test, if available

## Testing Status

Testing has not yet been completed. This section will be updated after implementation.
