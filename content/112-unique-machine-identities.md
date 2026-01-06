---
title: Unique Machine Identities for Agents
tags:
  - phase1
  - registration
  - identity
  - auditability
---

## The Principle

**Every agent instance must have its own unique identity.**

No two agents should share a service account. This is non-negotiable for:

- Clear audit trails
- Incident attribution
- Granular revocation
- Least privilege enforcement

## Why Shared Accounts Fail

When multiple agents share an identity:

| Problem | Impact |
|---------|--------|
| Audit confusion | "Which agent accessed this data?" |
| Over-permissioning | Shared account needs union of all permissions |
| Blast radius | Compromise affects all agents |
| Revocation difficulty | Can't disable one without disabling all |

## Agent Identity Components

Each agent identity has:

- **Object ID**: Unique GUID in the tenant
- **App ID**: Always equals object ID for agent identities
- **Display name**: Human-readable identifier
- **Credentials**: Federated (no passwords)
- **Sponsor**: Human accountability link

## Agent User (Optional)

Some systems require a *user* object, not a service principal. Agent identities can optionally have an **agent user** - a user object with 1:1 relationship to the agent identity.

Use case: Systems with hard dependency on UPN, manager attribute, Teams presence, etc.

---

## Links

- [[101-non-human-identity]] - Agents as NHI
- [[110-agent-identity-blueprints]] - Blueprints create unique identities
- [[141-audit-reasoning-trace]] - Why unique IDs enable better auditing
- [[151-credential-revocation]] - Disabling individual agents

## Source

- [Agent identities in Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/agent-identities)
- [Agent users in Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/agent-users)
