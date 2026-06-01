# Access Risk Register

| Risk ID | Risk Description | Affected User/Group | Likelihood | Impact | Risk Level | Existing Control | Recommendation |
|---|---|---|---|---|---|---|---|
| IAM-R001 | Administrative access could allow full control over AWS resources if credentials are compromised. | cloud-grc-admin / CloudGRC-Admins | Medium | High | High | MFA enabled for cloud-grc-admin | Limit admin access, monitor sign-ins, and review admin membership regularly |
| IAM-R002 | Broad developer permissions may exceed required job responsibilities. | CloudGRC-Developers | Medium | High | High | Developer access separated into its own group | Replace PowerUserAccess with least-privilege policies based on required services |
| IAM-R003 | Users without regular access reviews may retain permissions longer than needed. | All IAM users | Medium | Medium | Medium | Group-based access assignment implemented | Perform periodic user and group membership reviews |
| IAM-R004 | Direct permission assignment could make access harder to manage. | IAM users | Low | Medium | Medium | Permissions assigned through groups | Continue using group-based access instead of direct user permissions |
| IAM-R005 | Lack of MFA on console users could increase account compromise risk. | IAM users with console access | Medium | High | High | MFA enabled for cloud-grc-admin | Enforce MFA for all users with console access |
| IAM-R006 | Read-only access may still expose sensitive configuration details. | CloudGRC-ReadOnly | Low | Medium | Low | ReadOnlyAccess assigned to separate group | Limit read-only access to users with a documented need |
| IAM-R007 | IAM activity may be difficult to investigate without audit visibility. | IAM users and groups | Medium | Medium | Medium | CloudTrail Event History reviewed | Maintain CloudTrail logging and review IAM-related activity regularly |