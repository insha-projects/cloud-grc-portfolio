# Findings and Recommendations

## Finding 1: Root User Secured with MFA

The AWS root user was secured using multi-factor authentication. This reduces the risk of unauthorized access to the highest-privilege identity in the AWS account.

### Risk

If the root user is compromised, an attacker could gain full administrative control of the AWS account.

### Recommendation

Use the root user only for account-level tasks. Daily lab work should be performed using the dedicated IAM admin user.

---

## Finding 2: IAM Admin User Created for Daily Lab Activity

A separate IAM admin user was created and assigned to the CloudGRC-Admins group. This supports better identity separation by reducing routine use of the root user.

### Risk

Using the root account for daily activity increases the impact of credential misuse and makes access governance weaker.

### Recommendation

Continue using the IAM admin user for project work and keep root credentials secured. Review admin access periodically.

---

## Finding 3: IAM Groups Demonstrate Access Segmentation

Three IAM groups were created: CloudGRC-Admins, CloudGRC-Developers, and CloudGRC-ReadOnly. This demonstrates role-based access separation.

### Risk

Broad permissions such as AdministratorAccess and PowerUserAccess may allow users to perform actions beyond their responsibilities.

### Recommendation

In a real environment, replace broad managed policies with least-privilege custom policies based on job responsibilities.

---

## Finding 4: Test Users Assigned Through IAM Groups

Test users were created and assigned to groups instead of receiving direct permissions. This supports better access management and easier permission review.

### Risk

If users are assigned permissions directly without group-based management, access reviews become more difficult and inconsistent.

### Recommendation

Continue assigning permissions through IAM groups and review user group membership regularly.

---

## Finding 5: S3 Bucket Public Access Is Blocked

The S3 bucket was created with Block Public Access enabled. This reduces the risk of accidental public exposure.

### Risk

Misconfigured S3 bucket permissions can expose stored data to unauthorized users or the public internet.

### Recommendation

Keep Block Public Access enabled unless there is a documented business requirement. Review bucket policies before storing sensitive information.

---

## Finding 6: S3 Default Encryption Is Enabled

The S3 bucket uses default server-side encryption with Amazon S3 managed keys.

### Risk

If encryption is not enabled, stored data may not be adequately protected at rest.

### Recommendation

Maintain default encryption for all S3 buckets. For higher-sensitivity data, evaluate stronger encryption and key management requirements.

---

## Finding 7: CloudTrail Event History Provides Audit Visibility

CloudTrail Event History was reviewed and showed recent AWS management events, including IAM-related activity.

### Risk

Without logging visibility, unauthorized or accidental activity may be difficult to investigate.

### Recommendation

For a future project phase, configure a dedicated CloudTrail trail with centralized log storage, retention requirements, and monitoring procedures.

---

## Finding 8: Budget Alert Supports Cost Governance

An AWS budget alert was created to help monitor unexpected spending.

### Risk

Cloud resources can create unexpected charges if paid services are launched or left running unintentionally.

### Recommendation

Review the Billing and Cost Management dashboard regularly and avoid paid resources unless required for a documented project objective.