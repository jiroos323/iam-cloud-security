# IAM Fundamentals

## What is Identity & Access Management?

IAM is a framework of policies, processes, and technologies that ensures the right people (and systems) have the right access to the right resources — at the right time.

---

## Core Concepts

### Authentication (AuthN)
Verifying **who you are**.
- Something you know (password)
- Something you have (hardware token, phone)
- Something you are (biometrics)

### Authorization (AuthZ)
Verifying **what you are allowed to do** after authentication.
- Enforced through roles, policies, and permissions

### Identity Lifecycle
1. **Provisioning** – Creating a user account with correct roles
2. **Active use** – User operates within assigned permissions
3. **Modification** – Role changes (e.g., promotion, department change)
4. **Deprovisioning** – Removing access when no longer needed (e.g., offboarding)

---

## Key Principles

### Least Privilege
Users should only have the **minimum permissions** required to do their job.
- Reduces the blast radius of a compromised account
- Example: A developer should not have Global Admin in Azure

### Separation of Duties (SoD)
No single person should be able to complete a sensitive task alone.
- Example: One person requests access, a different person approves it

### Zero Trust
"Never trust, always verify" — even internal users must authenticate.
- Assumes breach: verify every request regardless of network location
- Relies heavily on strong IAM controls

---

## Identity Types in Cloud

| Type | Description | Example |
|------|-------------|--------|
| **Human identity** | Real user accounts | Employee logging into Azure |
| **Service identity** | Application/workload identities | App using Managed Identity |
| **Device identity** | Registered/enrolled devices | Laptop joined to Entra ID |
| **External identity** | Guests, partners, customers | B2B guest user in Azure AD |

---

## Common Threats to IAM

- **Credential stuffing** – Using leaked passwords against accounts
- **Pass-the-hash** – Stealing hashed credentials for lateral movement
- **Privilege escalation** – Gaining more permissions than assigned
- **Shadow IT identities** – Unmanaged accounts outside IT control
- **Orphaned accounts** – Accounts not deprovisioned after offboarding
