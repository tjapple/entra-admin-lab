# User Creation (Entra ID)

## Purpose
Standard procedure for creating a new user identity in Microsoft Entra ID. This process mirrors MSP-level onboarding workflows for cloud-only environments.

## Scope
Applies to cloud-only Entra tenants without hybrid AD sync.

## Procedure

### 1. Navigate to User Management
- Open Azure Portal
- Go to **Microsoft Entra ID → Users**
- Select **New user**

### 2. Configure Identity Details
- **User principal name (UPN):** Set format `firstname.lastname@tenant.onmicrosoft.com`
- **Display name:** Match UPN naming convention
- **Password:** Auto-generate or create manually

### 3. Assign Group Memberships 
Add user to baseline security groups, such as:
- **All Staff**
- **Department-specific groups** (example: Marketing)
- **Role-based access groups** (example: IT Admins) — *only if applicable*

### 4. Apply Administrative Roles (If Required)
Add user to admin roles as needed:
- Assign *least-privileged roles only*
- Avoid granting **Global Administrator** except for breakglass accounts

### 5. Create User
- Finish user creation
- Click into user profile if anything needs changed in the future

### 6. Validate Account Creation
Checklist:
- [ ] User appears in All Users
- [ ] Group memberships applied
- [ ] Role assignments (if applicable)
- [ ] MFA enforced by policy

---

## Notes
- All identity creation must follow least-privilege principles.
- MFA must be enforced for all accounts except designated breakglass accounts.
- Account creation will automatically require the user to reset their password and set up MFA.
