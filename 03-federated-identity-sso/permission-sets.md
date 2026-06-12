# Permission Sets and Federated Role Design

## Purpose

This section documents the access design used in the project.

The original project plan considered AWS IAM Identity Center permission sets. During implementation, an account-level SAML federation model was selected instead to avoid creating an AWS Organization or changing the billing structure of the lab account.

The final implementation uses an AWS IAM federated role with read-only permissions.

## Implemented Access Design

| Access Component | Configuration |
|---|---|
| Identity Provider | Okta |
| Federation Protocol | SAML 2.0 |
| AWS Trust Component | AWS IAM SAML Identity Provider |
| AWS Federated Role | Okta-ReadOnlyAudit-Role |
| AWS Managed Policy | ReadOnlyAccess |
| Assigned Okta Group | Cloud-Auditors |

## Federated Role

The AWS IAM role created for this project was:

`Okta-ReadOnlyAudit-Role`

This role trusts the Okta SAML identity provider and allows assigned Okta users to access the AWS Management Console through federation.

## Permission Policy

The role was assigned the AWS managed policy:

`ReadOnlyAccess`

This policy allows visibility into AWS resources without granting permission to create, modify, or delete resources.

## Least Privilege Rationale

The Cloud-Auditors group represents users who need visibility into AWS resources for audit, compliance, and review purposes.

These users do not require administrative access. Assigning read-only permissions supports least privilege by allowing evidence collection and configuration review without allowing changes to the AWS environment.

## Validation

Least privilege was validated by attempting to create an IAM user from the federated read-only session.

AWS denied the action because the role did not have permission to perform:

`iam:CreateUser`

This confirmed that the assigned role allowed console visibility but restricted administrative IAM actions.

## Production Recommendation

In a production environment, organizations may use AWS IAM Identity Center with permission sets across multiple AWS accounts.

Recommended production permission sets may include:

| User Group | Recommended Production Access |
|---|---|
| Cloud-Administrators | Administrator access with strict approval and MFA |
| Cloud-Developers | Limited developer access based on environment |
| Cloud-Security | Security audit and monitoring access |
| Cloud-Auditors | Read-only audit access |

Custom permission sets should be preferred over broad managed policies when precise least privilege is required.
