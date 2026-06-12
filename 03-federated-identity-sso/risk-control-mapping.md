# Risk and Control Mapping

## Purpose

This section maps common cloud identity and access risks to security controls demonstrated in this project.

The goal is to show how federated identity, SAML-based single sign-on, role-based access, and read-only access validation support cloud governance and compliance.

## Risk and Control Mapping

| Risk | Impact | Control Demonstrated | Control Objective |
|---|---|---|---|
| Long-term IAM user credentials are used for workforce access | Increased risk of credential theft or unmanaged access | Okta SAML federation with AWS IAM role assumption | Reduce reliance on long-term IAM user credentials |
| Users are assigned excessive AWS permissions | Unauthorized changes, privilege misuse, or accidental misconfiguration | Read-only federated role using AWS ReadOnlyAccess policy | Ensure users receive access based on business need |
| Access is granted without clear role mapping | Poor audit visibility and inconsistent access decisions | Okta group assignment mapped to AWS federated role | Document who receives access and why |
| Auditors need AWS visibility without modification rights | Evidence collection may require unnecessary elevated access | Okta-ReadOnlyAudit-Role assigned to Cloud-Auditors | Allow audit visibility without change permissions |
| Unauthorized IAM changes are attempted | Identity controls could be bypassed or misused | AWS denied iam:CreateUser for the federated read-only role | Validate least privilege enforcement |
| Identity provider trust is not documented | Weak audit evidence for federated access | AWS SAML Identity Provider configured for Okta | Document trust relationship between Okta and AWS |

## Framework Alignment

| Framework / Standard | Relevant Area | Project Alignment |
|---|---|---|
| ISO 27001 | Access control and identity management | Supports controlled access based on business need |
| NIST Cybersecurity Framework | Protect: Identity Management and Access Control | Demonstrates centralized identity, federation, and least privilege |
| CIS AWS Foundations Benchmark | IAM and access management | Supports reduced use of long-term IAM users and controlled role-based access |
| SOC 2 Security Criteria | Logical access controls | Demonstrates access authorization, role-based access, and validation of restricted actions |

## Governance Notes

Access should be granted based on approved business need and reviewed regularly.

Privileged access should be limited, monitored, and protected with multi-factor authentication.

Federated access should be documented with evidence showing the identity provider, AWS trust relationship, assigned role, and access validation results.

In a production environment, organizations should use dynamic user attributes, multiple roles, formal access approval workflows, and periodic access reviews.
