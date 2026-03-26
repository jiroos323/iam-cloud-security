# Lab 01: Configure MFA in Microsoft Entra ID

**Difficulty:** Beginner  
**Time:** ~30 minutes  
**Prerequisites:** Microsoft 365 Developer Tenant or Azure free account

---

## Objective

Configure Multi-Factor Authentication (MFA) for users in Microsoft Entra ID using Conditional Access policies.

---

## Steps

### 1. Create a test user
1. Go to [entra.microsoft.com](https://entra.microsoft.com)
2. Navigate to **Users → All users → New user**
3. Create a user: `testuser@yourdomain.onmicrosoft.com`
4. Note the temporary password

### 2. Create a Conditional Access Policy
1. Go to **Protection → Conditional Access → New policy**
2. Name: `Require MFA for All Users`
3. **Assignments:**
   - Users: Select your test user (or "All users" in a lab environment)
   - Cloud apps: "All cloud apps"
4. **Grant:**
   - Select "Grant access"
   - Check "Require multifactor authentication"
5. **Enable policy:** Set to "On"
6. Click **Save**

### 3. Test the policy
1. Open an InPrivate/Incognito browser
2. Go to [portal.azure.com](https://portal.azure.com)
3. Sign in as the test user
4. You should be prompted to set up MFA
5. Complete Microsoft Authenticator registration

---

## Expected Result

Test user cannot access any Microsoft cloud app without completing MFA — even with a correct password.

---

## Reflection Questions

- What happens if the user's phone is unavailable? (Hint: backup methods)
- How would you exclude break-glass accounts from this policy?
- What is the difference between per-user MFA and Conditional Access MFA?

---

## Notes

```
✅ Completed: [date]
Observations: 
Issues encountered:
```
