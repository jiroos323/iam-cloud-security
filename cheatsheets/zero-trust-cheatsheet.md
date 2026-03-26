# Zero Trust Cheatsheet

## Core Principles

| Principle | Meaning |
|-----------|---------|
| **Verify explicitly** | Always authenticate and authorize based on all available data points |
| **Use least privilege** | Limit user access with Just-In-Time (JIT) and Just-Enough-Access (JEA) |
| **Assume breach** | Minimize blast radius, segment access, verify end-to-end encryption |

---

## Zero Trust Pillars

```
┌─────────────┐  ┌─────────────┐  ┌─────────────┐
│  Identities │  │   Devices   │  │    Apps     │
└─────────────┘  └─────────────┘  └─────────────┘
┌─────────────┐  ┌─────────────┐  ┌─────────────┐
│   Network   │  │Infrastructure│  │    Data     │
└─────────────┘  └─────────────┘  └─────────────┘
         All managed via: Visibility & Automation
```

---

## Zero Trust vs Traditional Security

| | Traditional (Castle & Moat) | Zero Trust |
|-|----------------------------|-----------|
| Trust model | Trust inside perimeter | Never trust, always verify |
| Network perimeter | Hard boundary (firewall) | No perimeter |
| User trust | Trusted once on VPN | Verified every request |
| Lateral movement | Easy once inside | Segmented, limited |

---

## Microsoft Zero Trust Implementation

- **Identities** → Entra ID + Conditional Access + PIM
- **Devices** → Intune + Defender for Endpoint
- **Applications** → Defender for Cloud Apps (CASB)
- **Data** → Microsoft Purview (classification + DLP)
- **Network** → Azure Firewall + Network Segmentation
- **Infrastructure** → Defender for Cloud (CSPM)
