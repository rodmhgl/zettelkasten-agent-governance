# Owners, Sponsors, and Managers

#phase2 #governance #roles #accountability

## The Three Roles

Microsoft Entra Agent ID separates **technical administration** from **business accountability**. This prevents excessive permissions while ensuring oversight.

## Comparison Table

| Aspect | Owner | Sponsor | Manager |
|--------|-------|---------|---------|
| **Focus** | Technical config | Business lifecycle | Org hierarchy |
| **Can modify settings** | ✅ Yes | ❌ No | ❌ No |
| **Can manage credentials** | ✅ Yes | ❌ No | ❌ No |
| **Can enable/disable agent** | ✅ Yes | ✅ Yes | ❌ No |
| **Can delete agent** | ✅ Yes | ❌ No | ❌ No |
| **Can restore deleted** | ✅ Yes | ❌ No | ❌ No |
| **Can request access packages** | ❌ No | ❌ No | ✅ Yes |
| **Typical persona** | Developer, IT Pro | Product Manager, Business Owner | Team Lead |

## Owner Details

- Technical administrators handling operational aspects
- Can add/remove other owners and sponsors
- Service principals can also be owners (for automation)
- **Optional** during creation

## Sponsor Details

- Makes lifecycle decisions: renew, extend, retire
- Provides business justification for access requests
- Participates in security incident triage
- **Required** during creation
- Users or groups can be sponsors

## Manager Details

- Only applies to **agent users** (not agent identities)
- Enables organizational hierarchy views
- Can request access packages for their reporting agents
- Cannot modify or delete agents

---

## Links

- [[120-agent-sponsorship-model]] - Why sponsorship matters
- [[122-lifecycle-workflows]] - Automation when sponsors change
- [[131-access-packages]] - What managers can request

## Source

- [Administrative relationships in Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/agent-owners-sponsors-managers)
