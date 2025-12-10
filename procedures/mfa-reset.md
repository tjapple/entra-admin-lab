# MFA Reset (Microsoft Entra ID)

## Purpose
Standard procedure for resetting a user's multi-factor authentication settings when they are locked out or cannot complete MFA. 

## Scope
Applies to cloud-only Entra tenants using either:
- Security Defaults
- Conditional Access MFA requirements (optional)

---

## Procedure

### 1. Navigate to MFA Settings
- Open Azure Portal
- Go to **Microsoft Entra ID → Users**
- Select the affected user
- In the left menu, open **Authentication methods**

### 2. Reset the User’s MFA State
- Select the **Require re-register MFA** tab
- Confirm the action

This wipes all previously registered MFA methods (app, phone, etc.) and forces new enrollment at next sign-in.

### 3. (Optional) Remove Authentication Methods Manually
If the user still has stale methods listed:
- Delete all entries under **Authenticator app**, **Phone**, **Email**, **FIDO**, etc.

### 4. Additional MFA settings
- **Add authentication methods**: you can manually set additional MFA methods (phone, email, QR code, or Temporary Access Pass)
- **Reset Password**: reset the user's password if needed

### 5. Communicate Resolution to the User
Tell the user:
- Sign in at https://myaccount.microsoft.com
- They will be prompted to set up MFA again
- They must have their phone available

---

## Validation Checklist
- [ ] All old methods removed  
- [ ] User can log in to the portal using password or Temporary Access Password
- [ ] User is prompted to set up MFA during sign-in

---

## Notes
- Resetting MFA does **not** reset passwords.  
- Use this only when user has lost access to:
  - Authenticator app
  - Phone
  - Backup methods  
- Do **not** disable MFA globally to fix a single user.

