---
title: Zero Trust for Agents
tags:
  - pattern
  - security
  - zero-trust
  - architecture
---

## The Principle

**Never trust, always verify - even for agents.**

Zero Trust assumes breach and verifies every access request as if it originates from an uncontrolled network. Agents are no exception.

## Zero Trust Pillars Applied to Agents

| Pillar | Human Implementation | Agent Implementation |
|--------|---------------------|----------------------|
| **Identity** | MFA, passwordless | Federated credentials, unique IDs |
| **Device** | Compliant device required | Compliant hosting platform |
| **Network** | Conditional Access by location | IP restrictions, private endpoints |
| **Application** | App protection policies | API permission scopes |
| **Data** | DLP, sensitivity labels | Scoped access, no bulk export |
| **Visibility** | Sign-in logs, risk detection | Agent logs, reasoning traces |

## Agent-Specific Zero Trust Controls

### Verify Explicitly

- Every agent request authenticated via Entra
- No shared credentials between agents (see [[112-unique-machine-identities]])
- Continuous Access Evaluation for real-time validation

### Use Least Privilege

- Delegated permissions over application permissions (see [[134-delegated-vs-application-permissions]])
- Time-bound access packages (see [[132-time-bound-access]])
- Scoped API permissions, never wildcard

### Assume Breach

- Risk-based Conditional Access (see [[133-conditional-access-agents]])
- Automated kill switch (see [[142-automated-kill-switch]])
- Comprehensive audit logging (see [[141-audit-reasoning-trace]])

## Trust Boundaries

```
┌─────────────────────────────────────────────────┐
│ Internet (Untrusted)                            │
└─────────────────────────────────────────────────┘
          │
          ▼ Conditional Access evaluation
┌─────────────────────────────────────────────────┐
│ Agent Identity Layer (Verify)                   │
│ • Blueprint validation                          │
│ • Sponsor attestation                           │
│ • Risk score check                              │
└─────────────────────────────────────────────────┘
          │
          ▼ Permission scope enforcement
┌─────────────────────────────────────────────────┐
│ Resource Layer (Authorize)                      │
│ • API permission validation                     │
│ • Data classification enforcement               │
│ • Rate limiting                                 │
└─────────────────────────────────────────────────┘
```

## Implementation Checklist

```
☐ Every agent has unique identity
☐ Federated credentials (no secrets)
☐ CA policies target agent identities
☐ Risk detection enabled
☐ Time-bound access configured
☐ Audit logging comprehensive
☐ Kill switch tested
```

---

## Links

- [[102-entra-agent-id-overview]] - The identity foundation
- [[133-conditional-access-agents]] - Policy enforcement
- [[130-least-privilege-agents]] - Permission minimization

## Source

- [Microsoft Zero Trust guidance](https://learn.microsoft.com/en-us/security/zero-trust/)
- [Security for AI agents with Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/identity-professional/security-for-ai)
