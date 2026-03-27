# Authentication Protocols

## OAuth 2.0

OAuth 2.0 is an **authorization framework** that allows third-party apps to access resources on behalf of a user, without sharing credentials.

### Key Roles
| Role | Description |
|------|-------------|
| **Resource Owner** | The user who owns the data |
| **Client** | The application requesting access |
| **Authorization Server** | Issues tokens (e.g., Entra ID) |
| **Resource Server** | API or service being accessed |

### Common Grant Types
- **Authorization Code** – Most secure, used by web apps (+ PKCE for SPAs)
- **Client Credentials** – Machine-to-machine (no user involved)
- **Device Code** – For devices with limited input (e.g., smart TVs)

> ⚠️ **Implicit flow** is deprecated avoid it in new applications.

---

## OpenID Connect (OIDC)

OIDC is an **identity layer on top of OAuth 2.0**. While OAuth 2.0 handles authorization, OIDC adds **authentication** it tells the application *who* the user is.

- Returns an **ID Token** (JWT) containing user identity claims
- Used by Microsoft Sign-in, Google Login, GitHub OAuth

### ID Token claims (example)
```json
{
  "iss": "https://login.microsoftonline.com/...",
  "sub": "user-unique-id",
  "name": "Jim Ro",
  "email": "jim@example.com",
  "exp": 1710000000
}
```

---

## SAML 2.0

Security Assertion Markup Language XML-based protocol for **federated SSO** (Single Sign-On).

### Use Case
Commonly used in enterprise environments to allow employees to sign in once and access multiple applications (e.g., corporate SSO to Salesforce, Workday).

### SAML vs OIDC
| | SAML 2.0 | OIDC |
|-|----------|------|
| Format | XML | JSON / JWT |
| Age | 2005 | 2014 |
| Best for | Enterprise SSO | Modern apps, APIs |
| Mobile support | Poor | Good |

---

## Multi-Factor Authentication (MFA)

MFA requires **two or more verification factors**:

1. **Something you know** – Password, PIN
2. **Something you have** – Authenticator app, SMS, hardware key (FIDO2)
3. **Something you are** – Fingerprint, face recognition

### MFA Methods (Microsoft)
| Method | Security Level |
|--------|---------------|
| SMS / Phone call | Low (SIM swapping risk) |
| Microsoft Authenticator (push) | Medium |
| TOTP (time-based OTP) | Medium |
| FIDO2 / Passkeys | High (phishing-resistant) |
| Windows Hello for Business | High |

> 💡 **Best practice**: Move users away from SMS MFA toward FIDO2/passkeys.
