# Helpdesk Scenario: Disable or Offboard a User

## Description
A manager requests immediate removal of access for a departing employee or contractor.  
The goal is to disable access instantly while preserving the account for auditing, security, and potential data retention.

---

## Goal
Safely disable the user so they cannot:
- Sign in
- Access company data
- Use existing sessions
- Trigger MFA prompts

While preserving:
- Audit logs
- Identity metadata
- Group assignments (optional for record)
- User data (if linked services exist later)

---

# Steps to Disable User Access

### 1. Disable the Account
Azure Portal → Microsoft Entra ID → Users → select user  
- Open **Account status** 
- Toggle **Account enabled** → **No**

This immediately stops all authentication attempts.

---

### 2. Remove Role Assignments (If Any)
Open **Assigned roles**:
- Remove all admin roles
- Confirm user is now a “Member” with no elevated privileges

Never leave admin roles attached to disabled accounts.

---

### 3. Clear Active Sessions (Important)
Go to:
- User → **Overview**
- Click **Revoke sessions**

This forces logout from:
- Browsers
- Mobile apps
- Desktop clients

---

### 4. Remove Group Memberships (Optional but recommended)
User → **Groups**

Remove the user from groups that grant:
- App access
- Department-based access
- Security privileges

This prevents accidental re-enablement from granting access too soon.

---

### 5. Document Offboarding Status
Record in ticket (example):
- Account disabled  
- Roles removed  
- Sessions revoked  
- Groups removed  
- Manager notified  

---


# Expected Outcome
- User can no longer authenticate
- All existing sessions are invalidated
- No privileged access remains
- Identity is preserved for documentation and audit purposes

---

## Notes
- Blocking sign-in does not delete user data.
- Disabled accounts still appear in sign-in logs and audit logs.
- Never delete an account without checking the company’s retention policy.
