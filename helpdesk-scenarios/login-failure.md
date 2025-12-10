# Helpdesk Scenario: User Cannot Log In

## Description
A user reports that they cannot sign in to their Microsoft account. They claim their password is correct. They are stuck in a loop or receiving a generic “We couldn’t sign you in” message.


---

## Goal
Determine the reason for the failed sign-in and resolve it using:
- Password reset
- MFA reset (Temporary Access Pass)
- User status checks
- Sign-in log analysis

---

## Steps to Diagnose

### 1. Check Sign-In Logs
- Microsoft Entra ID → **Monitoring → Sign-in logs**
- Filter for the affected user
- Identify the status:
  - **Failure** → Open and inspect
  - **Interrupted** → Usually MFA-related
  - **Success** → User may be mistaken about the login step

### 2. Identify the Cause Based on Logs
Typical root causes:
- **Invalid password**
- **MFA failed or not set up**
- **User disabled**
- **User not found / wrong UPN**
- **Risk-based block**

### 3. Apply the Correct Fix
- **Invalid password:**  
  Reset the user’s password in Entra.

- **MFA failure:**  
  Remove MFA methods and require the user to re-register (or issue a **Temporary Access Pass**).

- **User disabled:**  
  Re-enable the user in their profile.

- **Wrong username:**  
  Confirm correct UPN (common mistake: personal Microsoft accounts vs work/school accounts).

- **Risk-based block:**  
  Reset user's password and MFA or issue a TAP.

### 4. Validate Resolution
Ask the user to:
- Go to https://aka.ms/mysecurityinfo  
- Sign in  
- Register MFA if prompted  
- Verify access to portal and apps

---

## Expected Outcome
- User can sign in successfully.
- MFA registration occurs cleanly if required.
- Sign-in logs show successful authentication.

---

## Notes
- Always check the logs first — never guess.  
- Never disable MFA globally to “fix” one user.  
- Use a Temporary Access Pass for clean MFA re-enrollment.
