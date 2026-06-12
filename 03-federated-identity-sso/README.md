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

```text
Okta User
   ↓
Okta SAML Application
   ↓
AWS SAML Identity Provider
   ↓
AWS IAM Federated Role
   ↓
AWS Management Console
