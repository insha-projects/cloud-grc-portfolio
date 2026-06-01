# Least Privilege Recommendations

## Recommendation 1: Limit AdministratorAccess Usage

The `CloudGRC-Admins` group has the `AdministratorAccess` policy attached. This policy allows full administrative control over AWS resources.

### Risk

If an admin user's credentials are compromised, an attacker could make unauthorized changes across the AWS account.

### Recommendation

Use `AdministratorAccess` only for users who require full administrative control. Review admin group membership regularly and enforce MFA for all admin users.

---

## Recommendation 2: Replace PowerUserAccess with Task-Based Permissions

The `CloudGRC-Developers` group has the `PowerUserAccess` policy attached. This policy provides broad access and may exceed what a developer needs.

### Risk

Broad permissions increase the chance of accidental or unauthorized changes to cloud resources.

### Recommendation

Replace `PowerUserAccess` with least-privilege custom policies based on specific developer responsibilities. For example, a developer may only need access to selected services such as S3, CloudWatch, or limited EC2 actions.

---

## Recommendation 3: Continue Using Group-Based Access

The lab uses IAM groups to assign permissions instead of attaching permissions directly to users.

### Risk

Direct user permissions can make access reviews inconsistent and harder to manage.

### Recommendation

Continue assigning permissions through IAM groups. Review group membership periodically to ensure users have only the access they need.

---

## Recommendation 4: Enforce MFA for Console Access

The `cloud-grc-admin` user has console access and MFA enabled. The test users do not have console access, so MFA is not applicable to them in this lab.

### Risk

Any IAM user with console access but no MFA would be more vulnerable to unauthorized login if credentials are compromised.

### Recommendation

Require MFA for every IAM user with AWS Management Console access.

---

## Recommendation 5: Review IAM Access Periodically

IAM access should not be treated as a one-time configuration. Users, groups, and permissions should be reviewed regularly.

### Risk

Users may retain unnecessary access after their responsibilities change.

### Recommendation

Perform periodic access reviews to confirm that IAM users, group memberships, and permissions remain appropriate.

---

## Recommendation 6: Use CloudTrail for IAM Activity Review

CloudTrail Event History provides visibility into IAM-related activity such as user creation, group creation, and policy attachment.

### Risk

Without audit logs, unauthorized IAM changes may be harder to detect and investigate.

### Recommendation

Review IAM-related CloudTrail events regularly. In a future phase, configure a dedicated CloudTrail trail with centralized log storage and retention.