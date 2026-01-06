---
title: 130-Least Privilege for Agents
tags:
  - phase3
  - access-control
  - security
  - principle
---

## The Principle

**Agents should never have permanent, broad permissions.**

Every permission granted to an agent should be:

- **Necessary**: Required for the agent's function
- **Sufficient**: No more than required
- **Temporary**: Time-bound with explicit renewal
- **Audited**: Logged and reviewable

## Why Agents Are High Risk

Unlike humans who access systems interactively:

- Agents run 24/7 without fatigue
- Agents can process data at machine speed
- Compromised agents can exfiltrate massive volumes
- Agents may have API access humans don't

## Implementation Strategies

| Strategy | How It Helps |
|----------|--------------|
| [[131-access-packages]] | Bundle only required permissions |
| [[132-time-bound-access]] | Force periodic renewal |
| [[133-conditional-access-agents]] | Block based on context |
| [[134-delegated-vs-application-permissions]] | Prefer user-scoped access |

## The Permissions Hierarchy

From most to least privileged:

1. **Global admin** (never for agents)
2. **Application permissions** (agent's own identity)
3. **Delegated permissions** (on behalf of user)
4. **Constrained delegation** (specific scopes only)

Always prefer the lowest level that enables functionality.

## Anti-Patterns to Avoid

- ❌ "Give it admin just to make it work"
- ❌ Permanent API permissions with no expiry
- ❌ Shared service accounts across multiple agents
- ❌ Permissions inherited from over-privileged blueprints

---

## Links

- [[131-access-packages]] - Bundling permissions
- [[134-delegated-vs-application-permissions]] - Choosing permission types
- [[160-zero-trust-agents]] - The broader security model

## Source

- [Overview of Microsoft Graph permissions](https://learn.microsoft.com/en-us/graph/permissions-overview)
- [What is Microsoft Entra ID Governance?](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview)
