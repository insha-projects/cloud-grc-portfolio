# Risk and Control Mapping

## Purpose

This section maps common cloud identity and access risks to security controls implemented or demonstrated in this project.

The goal is to show how federated identity, single sign-on, role-based access, and permission sets support cloud governance and compliance.

## Risk and Control Mapping

| Risk | Impact | Control Implemented | Control Objective |
|---|---|---|---|
| Users are assigned excessive AWS permissions | Increased risk of unauthorized changes or privilege misuse | Role-based access through AWS IAM Identity Center permission sets | Ensure users receive access based on job responsibilities |
| Long-term IAM user credentials are used for employee access | Higher risk of credential theft or unmanaged access | Federated access through Okta and AWS IAM Identity Center | Reduce reliance on long-term credentials |
| Access is manually assigned without clear documentation | Poor audit visibility and inconsistent access decisions | Access control matrix | Document who should have access and why |
| Privileged access is not reviewed | Former or unnecessary admin access may remain active | Periodic access review recommendation | Confirm privileged access is still appropriate |
| Users can access systems without strong authentication | Increased account compromise risk | Okta authentication and MFA recommendation | Strengthen identity verification before AWS access |
| Auditors cannot verify access assignments | Compliance gaps during review or audit | Screenshot evidence and documented permission mappings | Provide audit-ready access governance evidence |

## Framework Alignment

| Framework / Standard | Relevant Area | Project Alignment |
|---|---|---|
| ISO 27001 | Access control and identity management | Supports controlled access based on business need |
| NIST Cybersecurity Framework | Protect: Identity Management and Access Control | Demonstrates centralized access management and least privilege |
| CIS AWS Foundations Benchmark | IAM and access management | Supports secure identity configuration and reduced use of long-term credentials |
| SOC 2 Security Criteria | Logical access controls | Demonstrates access authorization, role-based access, and review readiness |

## Governance Notes

Access should be granted based on approved business need and reviewed regularly.

Privileged access should be limited, monitored, and protected with multi-factor authentication.

In a production environment, access reviews should be performed on a scheduled basis and documented as compliance evidence.
