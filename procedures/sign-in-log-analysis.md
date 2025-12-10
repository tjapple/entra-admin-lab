# Sign-In Log Analysis

## Purpose
Provide a clear workflow for diagnosing login issues using Microsoft Entra Sign-in Logs. These logs are essential for troubleshooting (failed login, MFA issues, password problems, location-based anomalies, etc.).

---

## Procedure

### 1. Open the Sign-In Logs
- Azure Portal → Microsoft Entra ID
- Go to **Monitoring → Sign-in logs**

You will see a table of all user sign-ins with:
- Date & Time
- Status (success/failure)
- Application
- IP Address
- Location
- Conditional Access results (if CA exists)
- MFA requirements
- Device info

### 2. Filter for the Affected User
At the top:
- Click **Add filter**
- Select **User**
- Type/select the user experiencing issues

### 3. Identify Failure Reasons
Check the **Status** column:
- **Success** → Login was completed normally  
- **Failure** → Expand entry to see reason  
- **Interrupted** → Usually MFA or Conditional Access–related  

Common failure reasons:
- Wrong password  
- MFA denied / not completed  
- User blocked  
- Sign-in blocked by Security Defaults  
- Sign-in blocked due to risk  
- Location/device restriction (if CA policies exist)  

### 4. Open the Detailed Entry
Click any sign-in row → it shows:
- Failure reason  
- Authentication details  
- Conditional Access evaluation (if applicable)  
- User agent  
- IP address + location  
- Device (if registered)  

### 5. Determine the Root Issue
Use detail fields to isolate:
- **Password-related issues:** “Invalid username or password”
- **MFA issues:** “Authentication method required but missing”
- **Risk-based blocks:** “Sign-in blocked due to risk”
- **Location/device blocks:** Country or device mismatch
- **Account disabled:** “Account is disabled”

### 6. Take Appropriate Action
Depending on reason:
- Reset password  
- Reset MFA / issue Temporary Access Pass  
- Re-enable user  
- Adjust group membership  
- Address suspicious sign-in patterns  
- Confirm Security Defaults enforcement  

---

## Validation Checklist
- [ ] Logs filtered to the affected user  
- [ ] Failure reason identified  
- [ ] Root cause determined (password, MFA, device, location, etc.)  
- [ ] Correct remediation applied  
- [ ] User successfully logs in afterward  

---

## Notes
- Sign-in logs update quickly (within seconds).
- Use these logs before attempting random fixes.
- Rely on log analysis to avoid guesswork.
