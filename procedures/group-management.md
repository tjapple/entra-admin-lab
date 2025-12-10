# Group Management

## Purpose
Provide a clean, repeatable workflow for creating and managing security groups in Microsoft Entra ID. Groups are used for access control, application assignment, and organizing users logically.

---

## Procedure

### 1. Navigate to Groups
- Azure Portal → Microsoft Entra ID
- Select **Groups**

### 2. Create a New Group
- Click **New group**
- Group type: **Security**
- Name: Use a clear, functional naming convention  
  Examples:
  - All Staff
  - IT Admins
  - Contractors
  - Marketing
- Description: Optional but recommended
- Membership type:
  - **Assigned** (manual membership) — preferred for lab/testing
  - **Dynamic** (requires rules; not needed early on)
- Optionally add owners or members from here

Click **Create**.

### 3. Add Members to the Group
- Open the newly created group
- Select **Members**
- Click **Add members**
- Search and select the users to add

### 4. Review Group Settings (Optional)
You may explore but do not modify unless needed:
- **Owner(s)** — who manages the group
- **Azure roles** (only appears for role-assignable groups)
- **Applications** (groups used for app assignment)

### 5. Validate Membership
- Go to the user → **Groups**
- Confirm the group shows in the user’s memberships

---

## Validation Checklist
- [ ] Group created with correct type (Security)
- [ ] Users added to group
- [ ] Membership appears in both group view and user view
- [ ] No unwanted groups assigned

---

## Notes
- Dynamic groups are powerful but unnecessary for entry-level workflows.
- Many admin settings can be applied at the group (roles, admins, owners, units, applications, licenses, etc)
