# Permission Sets

## Purpose

Permission sets define the level of AWS access assigned to each user group through AWS IAM Identity Center.

This project uses permission sets to demonstrate role-based access control and least privilege access governance.

## Permission Set Design

| Permission Set | Assigned Group | AWS Managed Policy | Purpose |
|---|---|---|---|
| AdministratorAccess | Cloud Administrators | AdministratorAccess | Full administrative access for cloud platform administrators |
| DeveloperAccess | Cloud Developers | PowerUserAccess | Allows developers to manage AWS resources without full IAM administration rights |
| SecurityAuditAccess | Cloud Security | SecurityAudit | Allows security users to review security configurations, IAM settings, logs, and compliance evidence |
| ReadOnlyAuditAccess | Cloud Auditors | ReadOnlyAccess | Allows auditors to view AWS resources and configurations without making changes |

## Least Privilege Rationale

Each permission set is assigned based on job responsibilities.

Cloud administrators require full access to manage the environment. Developers require access to build and manage resources but should not have unrestricted identity management permissions. Security users require visibility into security configurations and logs. Auditors require read-only access to support evidence collection and compliance review.

## Privileged Access Consideration

Administrator access should be limited to a small number of authorized users. Users assigned to privileged permission sets should be reviewed regularly and protected with multi-factor authentication.

## Production Recommendation

In a production environment, custom permission sets should be created instead of relying only on broad AWS managed policies. Custom permission sets allow organizations to apply more precise least privilege controls based on business need.
