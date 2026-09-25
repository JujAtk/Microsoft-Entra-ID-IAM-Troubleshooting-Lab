# Microsoft Entra ID IAM Troubleshooting Lab

## Project Overview

This project simulates real-world Identity and Access Management (IAM) support tickets in Microsoft Entra ID. The goal was to practice investigating identity issues, identifying root causes, applying least-privilege principles, remediating access problems, and verifying that each issue was resolved.

The lab focuses on troubleshooting rather than only performing basic administrative tasks.

## Technologies Used

- Microsoft Entra ID
- Microsoft Entra Admin Center
- Microsoft Authenticator
- Role-Based Access Control (RBAC)
- Microsoft Entra Sign-In Logs
- MFA Number Matching
- Group-Based Access Management

## Ticket 1: Mover and Privilege Creep Remediation

### Scenario
An employee transferred from Finance to HR but retained Finance-related access from the previous role.

### Investigation
Reviewed the user's existing group memberships and identified stale Finance access.

### Remediation
- Added the user to the appropriate HR security group.
- Removed the old Finance employee group.
- Removed the Finance Accounts Payable entitlement.
- Verified that only the access required for the new HR role remained.

### IAM Concepts
- Joiner-Mover-Leaver (JML)
- Privilege creep
- Least privilege
- RBAC
- Group-based access control
- Access validation

---

## Ticket 2: Administrative Role Right-Sizing

### Scenario
An administrative account had more privileges than required for its job responsibilities.

### Investigation
Reviewed the account's Microsoft Entra directory role and found that User Administrator provided broader access than necessary.

### Remediation
- Removed the User Administrator role.
- Assigned Helpdesk Administrator.
- Verified that the account retained the permissions required for password and user support while reducing unnecessary administrative privileges.

### IAM Concepts
- Least privilege
- Privileged access management
- Role right-sizing
- Delegated administration
- Access review

---

## Ticket 3: Authentication Failure Investigation

### Scenario
A user reported being unable to sign in.

### Investigation
- Confirmed that the account was enabled.
- Reviewed Microsoft Entra sign-in logs.
- Identified sign-in error code 50126.
- Determined that authentication failed because of invalid credentials.
- Reviewed Conditional Access information to rule out a policy-based block.

### Remediation
- Reset the user's password.
- Completed the required authentication setup.
- Verified a successful sign-in through Microsoft Entra sign-in logs.

### IAM Concepts
- Authentication troubleshooting
- Sign-in log analysis
- Error-code investigation
- Password remediation
- Root-cause analysis
- Post-remediation validation

---

## Ticket 4: MFA Registration and Recovery

### Scenario
A user could not complete multifactor authentication because no usable authentication methods were registered.

### Investigation
Reviewed the user's authentication methods and confirmed that no usable MFA method or default authentication method existed.

### Remediation
- Required MFA re-registration.
- Registered Microsoft Authenticator.
- Tested Microsoft Authenticator number matching.
- Successfully completed MFA authentication.
- Verified Microsoft Authenticator as the user's usable and default authentication method.

### IAM Concepts
- Multifactor authentication
- MFA recovery
- Microsoft Authenticator
- Number matching
- Authentication methods
- User verification
- Post-remediation validation

---

## Troubleshooting Methodology

For each IAM ticket, I followed a consistent troubleshooting process:

1. Identify the reported problem.
2. Review the user's current identity and access state.
3. Gather evidence from Microsoft Entra.
4. Determine the root cause.
5. Apply the least-privileged remediation.
6. Verify that the change resolved the issue.
7. Document the final state.

## Skills Demonstrated

- Microsoft Entra ID Administration
- IAM Troubleshooting
- Identity Lifecycle Management
- Joiner-Mover-Leaver Processes
- Role-Based Access Control
- Least Privilege
- Privilege Creep Remediation
- Directory Role Management
- Sign-In Log Analysis
- Authentication Error Investigation
- Password Administration
- Multifactor Authentication
- Microsoft Authenticator
- Access Validation
- Root-Cause Analysis
- IAM Incident Remediation

## Screenshots

Screenshots documenting the investigation, remediation, and validation steps for each ticket are included in this repository.
