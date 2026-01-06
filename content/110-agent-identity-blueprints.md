---
title: 110-Agent Identity Blueprints
tags:
  - phase1
  - registration
  - blueprint
  - template
---

## What Is a Blueprint?

An agent identity blueprint is a **template** for creating agent identities. It defines the "type" or "class" of agent and records metadata shared across all instances of that type.

Think of it like a Kubernetes Deployment vs Pod relationship - the blueprint defines the spec, individual agent identities are the running instances.

## Four Purposes

1. **Template**: Stores common configuration (description, app roles, authentication settings)
2. **Factory**: Creates agent identities via `AgentIdentity.CreateAsManager` permission
3. **Credential holder**: Stores federated identity credentials used by all child agents
4. **Policy anchor**: Enables CA policies and governance rules for all agents of this type

## Example Scenario

Organization deploys a "Sales Assistant Agent":

- One **blueprint** called "Sales Assistant Agent"
- Multiple **agent identities**: NA-Sales, EU-Sales, Enterprise-Sales, SMB-Sales
- All share: display name pattern, permissions, risk policies
- Each unique: object ID, specific resource access, sponsor

## Blueprint Principal

When a blueprint is added to a tenant, it creates a **blueprint principal** - the in-tenant record that can instantiate agent identities.

---

## Links

- [[100-pets-vs-swarms]] - Why blueprints enable swarm management
- [[102-entra-agent-id-overview]] - The broader platform
- [[112-unique-machine-identities]] - Each instance still gets unique identity
- [[133-conditional-access-agents]] - Applying CA to blueprint types

## Source

- [Agent identity blueprints in Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/agent-blueprint)
- [Agent identity and blueprint concepts](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/key-concepts)
