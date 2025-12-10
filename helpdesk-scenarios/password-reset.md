# Helpdesk Scenario: Password Reset Request

## Description
A user reports that they cannot remember their password or are failing the password field repeatedly. They are not blocked by MFA, and sign-in logs show “Invalid username or password.”

---

## Goal
Reset the user’s password safely and ensure they can sign in again without creating additional issues.

---

## Steps to Diagnose

### 1. Verify User Identity
Internally, confirm the requester is the actual user.
Examples (varies by environment):
- Known phone extension
- Verified ticket submission
- Confirmed via manager
- Existing internal process

### 2. Check Sign-In Logs (Optional but good practice)
- Microsoft Entra ID → Monitoring → **Sign-in logs**
- Filter by user
- Look for:
  - **Failure: Invalid username or password**
  - **Interrupted: Requires MFA** (then use MFA reset procedure)

### 3. Reset the Password
Azure Portal:
- Microsoft Entra ID → **Users → select user**
- Click **Reset password**
- Generate a temporary password

Provide the temporary password securely according to policy.

---

## Steps to Resolve

### 4. User Signs In
User goes to:
- https://portal.office.com  
  or  
- https://myaccount.microsoft.com  

They will be prompted to:
- Enter temporary password
- Create a new password
- Complete MFA setup if required

### 5. Validate Success
Confirm:
- User logged in successfully
- No MFA issues

---

## Expected Outcome
- User can access their account with a new password
- Correct sign-ins show in sign-in logs
- No further authentication failures

---

## Notes
- Password reset does **not** affect MFA registrations.
- If MFA causes issues during sign-in, use the **MFA Reset** scenario.
- Always follow proper identity verification procedures before resetting a password.
