# Cloud GRC Portfolio

This repository contains hands-on Cloud Governance, Risk, and Compliance projects built in a personal AWS lab environment.

The purpose of this portfolio is to demonstrate practical cloud security and GRC skills, including risk assessment, IAM governance, access control review, federated identity, single sign-on, security control documentation, audit evidence collection, and compliance-style recommendations.

These projects are designed to show the connection between technical cloud security controls and governance, risk, and compliance practices.

## Portfolio Focus Areas

* Cloud security risk assessment
* IAM governance and access review
* Least privilege analysis
* Federated identity and single sign-on
* Role-based access control
* Security controls review
* Audit evidence collection
* CloudTrail event review
* AWS billing and cost governance
* Compliance-style documentation
* Risk register development
* Findings and recommendations reporting

## Projects

### 1. AWS Security Risk Assessment

This project presents a security and compliance assessment of a basic AWS cloud lab environment. It covers AWS account security, IAM users and groups, MFA, S3 bucket security, AWS Budgets, and CloudTrail Event History.

The project includes an asset inventory, risk register, security controls review, evidence index, and findings with recommendations.

**Key skills demonstrated:**

* AWS account security review
* S3 security assessment
* MFA validation
* CloudTrail evidence review
* Risk documentation
* Security control assessment
* Cost governance awareness

**Project folder:** [01-aws-security-risk-assessment](./01-aws-security-risk-assessment)

---

### 2. IAM Governance Review

This project presents an IAM governance review of a personal AWS cloud lab environment. It covers IAM users, IAM groups, attached policies, MFA status, group-based access assignment, access risks, and least-privilege recommendations.

The project includes an IAM user inventory, group permissions review, access risk register, evidence index, and least-privilege recommendations.

**Key skills demonstrated:**

* IAM access review
* Group-based permission analysis
* Least privilege evaluation
* MFA status review
* CloudTrail IAM event evidence
* Access risk documentation
* GRC-style recommendations

**Project folder:** [02-iam-governance-review](./02-iam-governance-review)

---

### 3. Federated Identity & SSO Implementation

This project demonstrates how federated identity and single sign-on can be used to manage AWS cloud access in a secure and audit-ready way.

The lab uses Okta as the identity provider and AWS IAM as the service provider through SAML federation. Instead of creating long-term IAM users for workforce access, users authenticate through Okta and assume a federated AWS IAM role.

The project includes Okta group and user setup, SAML application configuration, AWS SAML identity provider setup, a federated read-only IAM role, successful Okta-to-AWS login validation, and least privilege testing through an unauthorized IAM action attempt.

**Key skills demonstrated:**

* Federated identity implementation
* SAML-based single sign-on
* Okta identity provider configuration
* AWS SAML identity provider setup
* AWS IAM federated role configuration
* Role-based access control
* Least privilege validation
* Read-only access testing
* Audit evidence collection
* Cloud access governance documentation

**Project folder:** [03-federated-identity-sso](./03-federated-identity-sso)

## Tools and Services Used

* AWS Identity and Access Management
* AWS IAM SAML Identity Provider
* AWS IAM Federated Roles
* AWS Management Console
* Amazon S3
* AWS CloudTrail Event History
* AWS Budgets
* AWS Billing and Cost Management
* Okta Integrator Free Plan
* SAML 2.0
* GitHub
* Markdown documentation

## Skills Demonstrated Across This Portfolio

* Cloud GRC documentation
* AWS security fundamentals
* IAM governance
* Access control review
* Federated identity and SSO
* Role-based access control
* Least privilege validation
* Risk register development
* Security controls assessment
* Audit evidence collection
* Cloud compliance thinking
* Technical documentation
* Findings and recommendations reporting

## Governance and Compliance Themes

This portfolio connects hands-on AWS security work with common governance, risk, and compliance objectives, including:

* Identity and access management
* User access review
* Privileged access control
* Least privilege enforcement
* Cloud security monitoring
* Evidence-based control validation
* Risk identification and remediation planning
* Secure configuration review
* Audit readiness

## Disclaimer

All projects in this repository were created in a personal AWS lab environment for learning and portfolio purposes. No real company data, production systems, or sensitive information were used.

Sensitive details such as AWS account IDs, ARNs, email addresses, sign-in URLs, access keys, metadata URLs, and source IP addresses have been removed or blurred from screenshots before upload.
