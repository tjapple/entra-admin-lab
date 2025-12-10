# Helpdesk Scenario: User Locked Out of MFA

## Description
A user cannot complete multifactor authentication. Common complaints:
- “My phone was wiped/replaced.”
- “Authenticator app lost.”
- “I can’t approve the sign-in.”
- “I never set up MFA but it's asking for it.”
- “I’m stuck in an MFA loop.”

---

## Goal
Restore account access by resetting the user's MFA registration and guiding them through a clean re-enrollment.

---

## Steps to Diagnose

### 1. Check Sign-In Logs
Microsoft Entra → Monitoring → **Sign-in logs**
- Filter by user
- Look for:
  - **Interrupted** (common MFA error)
  - “Authentication method required but not configured”
  - “Unable to satisfy MFA requirement”
  - “Denied by user” (user pressed “Deny” in app)
  - Location mismatch or suspicious sign-in (may require TAP)

### 2. Confirm User Status
Check:
- The account is enabled
- No Conditional Access restrictions affecting them
- Security Defaults are enabled (common)

---

## Steps to Resolve

### 3. Reset All MFA Methods
Azure Portal:
- Microsoft Entra ID → Users → select user
- Open **Authentication methods**
- Click "Require re-register multifactor authentication"
- Delete all existing:
  - Authenticator app methods
  - Phone numbers
  - Email
  - FIDO keys

Goal: **User has zero MFA methods.**

### 4. Issue a Temporary Access Pass (TAP)
If user is fully locked out:
- Add authentication method -> Generate TAP:
  - One-time or multi-use
  - Set expiration (1 hour recommended)
    
If not available, ensure TAP is enabled as an authentication method:
- Microsoft Entra → Security → Manage -> Authentication methods → enable "Temporary Access Pass"

This lets the user sign in without MFA to re-enroll cleanly.

### 5. Guide User Through Re-Enrolling MFA
User goes to:
https://aka.ms/mysecurityinfo

Steps:
- Sign in using password or TAP
- Register Authenticator app
- Add phone number
- Ensure at least one backup method exists

---

## Expected Outcome
- User can log in successfully
- All MFA prompts now work correctly
- Sign-in logs show successful MFA completions

---

## Notes
- Never disable MFA globally to fix an individual user.
- TAP is the preferred modern recovery method.
- If a user repeatedly gets locked out, check for:
  - Device change  
  - Phone reset  
  - Location mismatches  
  - Account compromise risk
