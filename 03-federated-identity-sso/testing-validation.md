# Testing and Validation

## Purpose

Testing and validation confirm that users receive the correct AWS access based on their assigned group and federated role.

The goal is to verify that access is role-based, least privilege is applied, and users do not receive unnecessary permissions.

## Test Scenarios

| Test Case | User Group | Expected Result | Status |
|---|---|---|---|
| Okta user launches AWS SAML application | Cloud-Auditors | User is redirected from Okta to AWS through SAML | Completed |
| Federated AWS login | Cloud-Auditors | User successfully signs in to AWS using the Okta-ReadOnlyAudit-Role | Completed |
| Read-only access validation | Cloud-Auditors | User can access AWS console but cannot create IAM users | Completed |
| Unauthorized IAM action attempt | Cloud-Auditors | AWS blocks iam:CreateUser due to insufficient permissions | Completed |

## Validation Results

The Okta SAML application successfully redirected the assigned user to AWS.

AWS recognized the SAML assertion from Okta and allowed the user to assume the federated IAM role:

`Okta-ReadOnlyAudit-Role`

The user was able to access the AWS Management Console through the federated role.

To validate least privilege, the user attempted to create a new IAM user. AWS denied the action because the federated role only had read-only permissions.

This confirmed that the SAML federation flow worked and that the assigned role did not allow unauthorized administrative actions.

## Evidence Captured

Screenshots were captured for:

- Okta group creation
- Okta user creation
- Okta SAML application assignment
- AWS SAML identity provider configuration
- AWS federated IAM role
- Successful AWS federated login
- Access denied message for unauthorized IAM user creation

## Testing Status

Testing completed successfully.

The lab confirmed that Okta could act as the identity provider and AWS IAM could trust Okta through SAML federation to grant role-based access.
