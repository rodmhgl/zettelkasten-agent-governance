---
title: Conditional Access for Agents
tags:
  - phase3
  - access-control
  - conditional-access
  - policy
---

## What It Is

Conditional Access (CA) for Agent ID brings the same Zero Trust controls protecting human users to AI agents. CA evaluates agent access requests and enforces policies based on:

- Agent identity or blueprint type
- Risk level
- Target resource
- Network location
- Custom security attributes

## Agent-Specific CA Capabilities

Unlike workload identity CA (limited to service principals), Agent ID CA supports:

| Feature | User CA | Workload CA | Agent CA |
|---------|---------|-------------|----------|
| Risk-based policies | ✅ | ✅ | ✅ |
| Location controls | ✅ | ✅ | ✅ |
| Blueprint targeting | ❌ | ❌ | ✅ |
| Agent collections | ❌ | ❌ | ✅ |
| Agent user policies | ❌ | ❌ | ✅ |

## Common Policy Patterns

### Block High-Risk Agents

```
Conditions: Agent risk = High
Grant: Block access
```

### Restrict by Blueprint Type

```
Conditions: Blueprint = "Sales Agent"
Target: All resources
Grant: Require internal network
```

### Block Agent Authentication Entirely

For organizations not ready for agents:

```
Conditions: All agent identities
Grant: Block
```

## Policy Scoping Options

- **All agent identities**: Blanket policies
- **Select agents acting as users**: Target agent users specifically
- **Select by attributes**: Use custom security attributes
- **Select individual agents**: Fine-grained control

---

## Links

- [[113-autonomy-classification]] - Risk tiers drive CA policies
- [[140-agent-risk-detection]] - Risk scores trigger CA
- [[142-automated-kill-switch]] - CA as enforcement mechanism
- [[161-agent-conditional-access-policies]] - Implementation patterns

## Source

- [Conditional Access for Agent ID (Preview)](https://learn.microsoft.com/en-us/entra/identity/conditional-access/agent-id)
- [Conditional Access: Users, groups, agents, and workload identities](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-users-groups)
- [Conditional Access for workload identities](https://learn.microsoft.com/en-us/entra/identity/conditional-access/workload-identity)
