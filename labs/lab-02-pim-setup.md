# Lab 02: Configure Privileged Identity Management (PIM)

**Difficulty:** Intermediate  
**Time:** ~45 minutes  
**Prerequisites:** Entra ID P2 license (free with Microsoft 365 Developer Program)

---

## Objective

Set up Privileged Identity Management so that a user can request just-in-time (JIT) access to the Global Administrator role instead of having it permanently assigned.

---

## Steps

### 1. Enable PIM
1. Go to [entra.microsoft.com](https://entra.microsoft.com)
2. Search for **Privileged Identity Management**
3. Click **Consent to PIM** if first time

### 2. Make a role Eligible (not Active)
1. In PIM → **Entra ID roles → Roles**
2. Select **Global Administrator**
3. Click **Add assignments**
4. Assignment type: **Eligible**
5. Select your test user
6. Set duration (e.g., 1 hour for lab purposes)
7. Click **Assign**

### 3. Configure Role Settings
1. In PIM → **Entra ID roles → Settings**
2. Select **Global Administrator → Edit**
3. Configure:
   - Activation max duration: 1 hour
   - Require MFA on activation: ✅
   - Require justification: ✅
   - Require approval: ✅ (set yourself as approver)

### 4. Activate the role (as test user)
1. Log in as the test user
2. Go to PIM → **My roles → Eligible assignments**
3. Click **Activate** next to Global Administrator
4. Enter justification: "Testing PIM lab"
5. Wait for approval (approve it from your admin account)

---

## Expected Result

Test user gains Global Administrator access for 1 hour only, with a full audit trail logged in PIM.

---

## Reflection Questions

- What is the difference between an **eligible** and **active** role assignment?
- Why is requiring justification important from a security perspective?
- How does PIM reduce the risk of a compromised admin account?

---
