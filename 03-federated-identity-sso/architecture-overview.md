# Architecture Overview

## High-Level Architecture

This project uses a federated identity model where users authenticate through Okta and access AWS through AWS IAM Identity Center.

The goal is to avoid creating separate long-term IAM users for each employee and instead use centralized authentication, role-based access, and temporary AWS access sessions.

## Architecture Flow

```text
User
 ↓
Okta
Identity Provider
 ↓
AWS IAM Identity Center
Service Provider
 ↓
AWS Account
 ↓
Permission Sets
Admin, Developer, Security, Auditor
