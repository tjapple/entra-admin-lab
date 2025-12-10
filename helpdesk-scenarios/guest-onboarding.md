# Helpdesk Scenario: Guest User Onboarding

## Description
A manager requests access for a non-employee. This could be:
- A vendor requiring limited access
- An external partner collaborating on a project


## Goal
Invite an external identity into Entra as a guest for collaboration.

---

## Steps

### 1. Invite Guest User
Microsoft Entra → Users → **New user → Invite external user**

Enter:
- Guest email address
- Optional welcome message

UPN appears as:
`email_com#EXT#@tenant.onmicrosoft.com`

### 2. Assign Groups or App Access
Guests are typically given:
- One security group  
- SharePoint/Teams access (if available)

They **should not** get admin roles.

### 3. Confirm Invitation Status
User → Overview shows:
- Creation type: **Invitation**

Manager confirms they logged in successfully.

### 4. Limit Guest Privileges
Guests are external:
- No directory write access  
- No admin functions  
- No ability to elevate permissions  

### 5. Remove Access When Complete
For guest offboarding:
- Remove group memberships
- Block sign-in
- Delete guest account

---

# Expected Outcome
The external partner can access only the required resources with no risk to internal systems.

---

## Notes
- Guests = external identities (Azure B2B)  
- Should not have admin roles  
- Should use MFA  
- Should be offboarded promptly 
