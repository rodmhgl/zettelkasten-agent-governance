# Access Packages for Agents

#phase3 #access-control #entitlement #bundle

## What Is an Access Package?

An access package is a **bundle of resources** that can be requested as a unit:
- Group memberships
- Application role assignments
- SharePoint site access
- API permissions (via groups)

## Why Bundle Permissions?

Instead of granting individual permissions:

| Without Packages | With Packages |
|------------------|---------------|
| Grant group A | Request "Sales Agent Package" |
| Grant app role B | (includes A, B, C, D) |
| Grant API scope C | Single approval workflow |
| Grant site access D | Single expiration policy |

## Access Package Components

```
Access Package: "HR Analytics Agent"
├── Resources
│   ├── Group: HR-Data-Readers
│   ├── App Role: Analytics-Viewer
│   └── SharePoint: HR-Reports (Read)
├── Policy
│   ├── Who can request: Agent Managers
│   ├── Approval: HR Director
│   └── Expiration: 180 days
└── Access Reviews
    └── Quarterly sponsor attestation
```

## Lifecycle Settings

| Setting | Agent Recommendation |
|---------|----------------------|
| **Expiration** | 90-180 days max |
| **Renewal** | Require re-request with justification |
| **Extension** | Require sponsor approval |
| **Access reviews** | Enable, quarterly minimum |

## Connection to Agent Governance

1. **Managers** can request packages for their agent users (see [[121-owners-sponsors-managers]])
2. **Sponsors** attest during access reviews (see [[123-access-reviews-recertification]])
3. **Expiration** enforces time-bound access (see [[132-time-bound-access]])

---

## Links

- [[130-least-privilege-agents]] - Why bundling matters
- [[132-time-bound-access]] - Expiration policies
- [[121-owners-sponsors-managers]] - Who requests packages

## Source

- [Create an access package in entitlement management](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-access-package-create)
- [Manage external access with Microsoft Entra entitlement management](https://learn.microsoft.com/en-us/entra/architecture/6-secure-access-entitlement-managment)
