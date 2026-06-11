# Business Scenario

## Background

A growing organization is moving away from manually managed AWS IAM users and wants to implement centralized cloud access using single sign-on.

The organization wants employees to authenticate through a trusted identity provider and receive access to AWS based on their job function. This reduces the use of long-term credentials, improves access visibility, and supports audit-ready identity governance.

## Business Problem

The current access model creates several risks:

- Users may have excessive permissions.
- Access may not be consistently reviewed.
- Manual user management can lead to delayed removal of access.
- Privileged access may not be clearly documented.
- Auditors may not have a clear view of who has access to AWS.

## Proposed Solution

This project implements a federated identity and single sign-on model using Okta as the identity provider and AWS IAM Identity Center as the AWS access management service.

Users will be organized into groups based on job function, and each group will be assigned an appropriate AWS permission set using least privilege principles.

## Project Scope

This lab uses a single AWS account to simulate enterprise cloud access governance. The same model can be scaled across multiple AWS accounts in a production environment.

The project focuses on:

- Centralized identity management
- Single sign-on access to AWS
- Role-based access control
- Permission set assignment
- Least privilege access
- Access review readiness
- Audit evidence documentation
