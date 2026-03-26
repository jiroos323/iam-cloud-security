# Microsoft Entra ID (formerly Azure Active Directory)

## What is Entra ID?

Microsoft Entra ID is Microsoft's cloud-based **Identity and Access Management** service. It is the backbone for identity in Microsoft 365, Azure, and thousands of third-party SaaS applications.

> ⚠️ Azure Active Directory was rebranded to **Microsoft Entra ID** in 2023.

---

## Key Components

### Users
- **Member users** – Internal users (employees)
- **Guest users** – External partners/vendors (B2B collaboration)
- **Service principals** – Non-human identities for apps/services
- **Managed Identities** – Azure-managed identities for resources (no password management needed)

### Groups
- **Security groups** – Used for assigning permissions to resources
- **Microsoft 365 groups** – For collaboration (Teams, SharePoint)
- **Dynamic groups** – Membership automatically managed based on user attributes

### Applications
- **App registrations** – Registering an app to use Entra ID for auth
- **Enterprise applications** – Pre-integrated SaaS apps (Salesforce, Dropbox, etc.)

---

## Entra ID Licenses

| Feature | Free | P1 | P2 |
|---------|------|-------|-----|
| Basic user management | ✅ | ✅ | ✅ |
| MFA | ✅ | ✅ | ✅ |
| Conditional Access | ❌ | ✅ | ✅ |
| Identity Protection | ❌ | ❌ | ✅ |
| Privileged Identity Management (PIM) | ❌ | ❌ | ✅ |

---

## Role-Based Access Control (RBAC) in Azure

RBAC controls who can do what on which resources.

### Built-in roles
- **Owner** – Full access including delegating access
- **Contributor** – Can manage resources, cannot change access
- **Reader** – Read-only access
- **User Access Administrator** – Can manage user access to Azure resources

### Assignment scope
```
Management Group
  └── Subscription
        └── Resource Group
              └── Resource
```
Roles assigned at a higher scope are **inherited** downward.

---

## Conditional Access

Conditional Access is Azure's **policy engine** for access decisions.

### Structure: If-Then
- **IF** (signals: user, location, device, app, risk)
- **THEN** (grant, block, require MFA)

### Common Policies
- Require MFA for all admin accounts
- Block access from untrusted/unknown locations
- Require compliant device for sensitive apps
- Block legacy authentication protocols

---

## Privileged Identity Management (PIM)

PIM provides **just-in-time (JIT) privileged access** to Azure AD and Azure resources.

### How it works
1. User is assigned an **eligible role** (not active by default)
2. User **activates** the role when needed (with justification + MFA)
3. Access is granted for a **limited time window**
4. Access expires automatically

### Benefits
- Reduces standing privileges
- Provides audit trail of privileged actions
- Requires approval workflow for sensitive roles
