# Identity Model Overview: AD DS, Entra ID, Microsoft 365, and Azure

## Purpose
Provide a clear explanation of how Microsoft’s modern identity systems fit together:
- On-premises Active Directory (AD DS)
- Microsoft Entra ID (formerly Azure AD)
- Microsoft 365 (M365)
- Azure

This helps clarify what functions each system performs and how they interact in real IT environments.

---

# 1. Active Directory Domain Services (AD DS)
AD DS is the on-premises identity directory used inside corporate networks.

### Key Characteristics
- Domain-joined Windows devices
- Kerberos/NTLM authentication
- Organizational Units (OUs)
- Group Policy (GPO)
- File shares, printers, and internal applications

### Important Point
AD DS does **not** communicate with Microsoft 365 or Azure automatically.  
It becomes part of the cloud identity model only if an organization chooses to synchronize it.

---

# 2. Microsoft Entra ID (Cloud Identity)
Entra ID is Microsoft’s cloud-based identity and access management platform.

### What It Provides
- Users and groups (cloud identities)
- MFA, Conditional Access, Sign-in logs
- Device identities (Entra join)
- SSO for Microsoft 365 and third-party apps
- Admin roles and RBAC
- Authentication for Azure resources

### Crucial Distinction
Entra ID is **not** the cloud version of AD DS.  
It has:
- No OUs  
- No GPO  
- No domain join (unless using Entra Join)  

Entra ID is built for **cloud-first authentication**, not Windows LAN management.

---

# 3. Microsoft 365 (Product Suite, Not an Identity System)
Microsoft 365 is a bundle of cloud applications:
- Exchange Online
- Teams
- SharePoint
- OneDrive
- Office apps

### Key Insight
- Microsoft 365 **depends on Entra ID** for all identity and authentication.
- Microsoft 365 does **not store users**.  
- All users, groups, and auth live inside Entra ID.
- The M365 Admin Center is essentially a UI layer on top of Entra ID + app-specific admin portals.

---

# 4. Azure (Cloud Computing Platform)
Azure provides:
- Virtual machines  
- Networks  
- Storage  
- Databases  
- Security and monitoring tools  

### Identity Backbone
Azure uses Entra ID for:
- Logging into the Azure portal
- Assigning access to resources (RBAC)
- Managing service principals and apps

Azure does **not** store or create users by itself; it consumes Entra ID identities.

---

# 5. How They Connect

### A. Microsoft 365 → Entra ID
This connection is automatic:
- Every M365 tenant has an Entra ID tenant
- Licenses determine which M365 apps a user can access
- User lifecycle happens in Entra ID first

### B. Azure → Entra ID
Azure trusts Entra ID for all authentication and authorization.

### C. AD DS → Entra ID (Optional Sync)
Organizations may synchronize AD DS into Entra ID using:
- Entra Connect (Azure AD Connect)
- Password Hash Sync or Pass-Through Authentication

This creates **hybrid identity**, where:
- AD DS is the “source of truth”
- Entra ID holds synchronized copies for cloud login

---

# 6. Model Summary

- Entra ID = Cloud identity system  
Used by Microsoft 365 and Azure.

- Microsoft 365 = Applications  
Exchange, Teams, SharePoint — all authenticate through Entra ID.

- Azure = Cloud computing platform  
Uses Entra ID identities to secure resources.

- AD DS = Internal identity system  
Optional; can be synchronized, but is not required for cloud identity.
