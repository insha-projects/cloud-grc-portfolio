# Federated Identity & SSO Implementation for AWS Cloud Access Governance

## Project Overview

This project demonstrates how federated identity and single sign-on can be used to manage AWS cloud access in a secure and audit-ready way.

The lab uses Okta as the identity provider and AWS IAM as the service provider through SAML federation. Instead of creating long-term IAM users for workforce access, users authenticate through Okta and assume a federated AWS IAM role.

The project focuses on centralized identity, role-based access, least privilege, and evidence-based access validation.

## Business Scenario

A growing organization wants to reduce reliance on manually managed AWS IAM users and improve access governance for cloud environments.

The organization needs a way to allow auditors and security reviewers to access AWS without granting unnecessary administrative permissions.

This project simulates a solution where users authenticate through Okta and receive read-only AWS access through a federated IAM role.

## Architecture

Okta User
↓
Okta SAML Application
↓
AWS SAML Identity Provider
↓
AWS IAM Federated Role
↓
AWS Management Console

## Tools and Services Used

| Tool / Service            | Purpose                                                 |
| ------------------------- | ------------------------------------------------------- |
| Okta Integrator Free Plan | Identity provider and SAML application configuration    |
| AWS IAM                   | SAML identity provider and federated role configuration |
| AWS Management Console    | Access validation and role testing                      |
| GitHub                    | Project documentation and evidence organization         |

## Implementation Summary

The project included the following steps:

1. Created Okta groups for cloud access roles.
2. Created Okta test users.
3. Assigned users to Okta groups.
4. Created a SAML application in Okta for AWS federation.
5. Created an AWS SAML identity provider using Okta metadata.
6. Created an AWS IAM federated role with read-only permissions.
7. Added AWS role attributes to the Okta SAML application.
8. Assigned the AWS SAML app to the Cloud-Auditors group.
9. Tested Okta-to-AWS federated login.
10. Validated least privilege by attempting an unauthorized IAM action.

## Access Model

| Okta Group     | AWS Role                | Permission Level | Purpose                                             |
| -------------- | ----------------------- | ---------------- | --------------------------------------------------- |
| Cloud-Auditors | Okta-ReadOnlyAudit-Role | ReadOnlyAccess   | Allows audit visibility without modification rights |

## Validation Results

The Okta SAML application successfully redirected the assigned user to AWS.

AWS recognized the SAML assertion and allowed the user to assume the federated IAM role.

The user successfully accessed the AWS Management Console using the role:

`Okta-ReadOnlyAudit-Role`

To validate least privilege, the user attempted to create an IAM user. AWS denied the action because the federated role did not have `iam:CreateUser` permissions.

This confirmed that the federation flow worked and that read-only access restrictions were enforced.

## Evidence Captured

Screenshots were captured for:

* Okta groups
* Okta users
* Okta SAML application
* AWS SAML identity provider
* AWS IAM federated role
* Successful AWS federated login
* Access denied validation for unauthorized IAM user creation

## Key Security Concepts Demonstrated

* Federated identity
* Single sign-on
* SAML-based authentication
* Role-based access control
* Least privilege
* Reduced reliance on long-term IAM users
* Access governance
* Audit evidence collection

## Governance and Compliance Relevance

This project supports common GRC and security control objectives related to identity and access management.

It demonstrates how centralized identity and federated access can help organizations improve access visibility, reduce credential risk, and support audit readiness.

Relevant areas include:

* Access control
* User access review
* Privileged access management
* Identity provider trust
* Cloud access governance
* Evidence-based compliance validation

## Project Status

Completed.
