# Azure RBAC Cheatsheet

## Built-in Role Hierarchy

```
Owner > Contributor > Reader
```

| Role | Read | Write | Delete | Manage Access |
|------|------|-------|--------|---------------|
| Owner | ✅ | ✅ | ✅ | ✅ |
| Contributor | ✅ | ✅ | ✅ | ❌ |
| Reader | ✅ | ❌ | ❌ | ❌ |
| User Access Admin | ✅ | ❌ | ❌ | ✅ |

---

## Scope Levels (Broad → Narrow)

```
Management Group  (/providers/Microsoft.Management/managementGroups/...)
  Subscription    (/subscriptions/{id})
    Resource Group (/subscriptions/{id}/resourceGroups/{rg})
      Resource    (/subscriptions/{id}/resourceGroups/{rg}/providers/...)
```

---

## Common Azure CLI Commands

```bash
# List role assignments for a user
az role assignment list --assignee user@domain.com

# Assign a role
az role assignment create \
  --assignee user@domain.com \
  --role "Contributor" \
  --scope /subscriptions/{sub-id}/resourceGroups/{rg-name}

# Remove a role
az role assignment delete \
  --assignee user@domain.com \
  --role "Contributor" \
  --scope /subscriptions/{sub-id}

# List all built-in roles
az role definition list --query "[].{Name:roleName}" -o table
```

---

## Privileged Roles to Watch

| Role | Risk | Notes |
|------|------|-------|
| Global Administrator | 🔴 Critical | Full tenant control |
| Privileged Role Administrator | 🔴 Critical | Can assign any role |
| Application Administrator | 🟠 High | Can add credentials to apps |
| Exchange Administrator | 🟡 Medium | Access to all mailboxes |

> ✅ Use PIM to make these roles eligible-only, not permanent.
