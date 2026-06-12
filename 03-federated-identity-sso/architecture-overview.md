# Architecture Overview

## High-Level Architecture

This project uses a federated identity model where users authenticate through Okta and access AWS through a SAML-based AWS IAM role.

The goal is to avoid creating separate long-term IAM users for workforce access and instead use centralized authentication, role-based access, and temporary AWS console sessions.

## Architecture Flow

Okta User  
↓  
Okta SAML Application  
↓  
AWS SAML Identity Provider  
↓  
AWS IAM Federated Role  
↓  
AWS Management Console  

## Component Description

| Component | Purpose |
|---|---|
| Okta User | Represents a workforce user who needs AWS access |
| Okta Group | Organizes users based on business role |
| Okta SAML Application | Sends the SAML assertion to AWS |
| AWS SAML Identity Provider | Establishes trust between AWS and Okta |
| AWS IAM Federated Role | Defines what AWS permissions the federated user receives |
| ReadOnlyAccess Policy | Provides read-only visibility into AWS resources |
| AWS Management Console | The AWS environment accessed through federation |

## Identity and Access Model

Users are assigned to Okta groups based on job function.

For this lab, the `Cloud-Auditors` group was assigned to the `AWS SAML Federation Lab` application. The application passed the AWS role attribute to AWS, allowing the user to assume the `Okta-ReadOnlyAudit-Role`.

The role was configured with the AWS managed `ReadOnlyAccess` policy.

## Lab Design Note

The original design considered AWS IAM Identity Center permission sets. During implementation, an account-level SAML federation model was selected to avoid creating an AWS Organization or changing the lab account billing structure.

This project uses one AWS account for safe lab implementation. In a production environment, this design could be expanded using AWS IAM Identity Center across multiple AWS accounts such as development, staging, production, and audit accounts.
