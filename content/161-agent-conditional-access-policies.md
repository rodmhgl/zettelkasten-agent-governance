# Agent Conditional Access Policy Patterns

#pattern #conditional-access #implementation #policies

## Overview

Common CA policy patterns for agent identity governance. These build on [[133-conditional-access-agents]] with specific implementation examples.

---

## Pattern 1: Block All Agents (Opt-In Model)

Start restrictive, enable agents explicitly.

```
Name: BLOCK - All Agent Identities (Default)
Users: All agent identities
Cloud apps: All cloud apps
Conditions: None
Grant: Block
```

Then create allow policies for approved blueprints/agents.

---

## Pattern 2: Risk-Based Kill Switch

Automatically block high-risk agents.

```
Name: BLOCK - High Risk Agents
Users: All agent identities
Cloud apps: All cloud apps
Conditions:
  - Agent risk: High, Critical
Grant: Block
Session: Revoke refresh tokens
```

---

## Pattern 3: Blueprint-Scoped Access

Limit agent types to specific resources.

```
Name: ALLOW - Sales Agents to CRM Only
Users: 
  - Include: Sales Agent blueprint
Cloud apps:
  - Include: Dynamics 365 Sales
Conditions: None
Grant: Allow
```

---

## Pattern 4: Network Restriction

Agents only from trusted networks.

```
Name: REQUIRE - Internal Network for Action Agents
Users:
  - Include: Agents with action-oriented classification
Cloud apps: All cloud apps
Conditions:
  - Locations:
    - Include: All locations
    - Exclude: Corporate network, Azure backbone
Grant: Block
```

---

## Pattern 5: Session Frequency

Force frequent re-authentication.

```
Name: SESSION - Agent Sign-In Frequency
Users: All agent identities
Cloud apps: All cloud apps
Conditions: None
Grant: Allow
Session:
  - Sign-in frequency: 1 hour
  - Persistent browser session: Disabled
```

---

## Pattern 6: Sensitive Data Protection

Extra controls for agents accessing classified data.

```
Name: REQUIRE - Confidential Data Access
Users: All agent identities
Cloud apps:
  - Include: Apps with sensitivity label "Confidential"
Conditions: None
Grant:
  - Require compliant hosting platform
  - Require risk level: None or Low
```

---

## Policy Naming Convention

Recommend structured naming:

```
{ACTION} - {DESCRIPTION} [{SCOPE}]

Examples:
BLOCK - All Agent Identities (Default)
ALLOW - HR Agents to Workday [HR Blueprint]
REQUIRE - Low Risk for PII Access
SESSION - 1 Hour Frequency for All Agents
```

---

## Deployment Order

1. **BLOCK all** (default deny)
2. **ALLOW specific** blueprints to specific apps
3. **REQUIRE** additional controls for sensitive access
4. **SESSION** controls for all
5. **BLOCK high risk** (kill switch)

Test in report-only mode before enforcement.

---

## Links

- [[133-conditional-access-agents]] - CA fundamentals for agents
- [[113-autonomy-classification]] - Classification drives policies
- [[142-automated-kill-switch]] - Risk-based blocking
- [[160-zero-trust-agents]] - Overall security model

## Source

- [Conditional Access for Agent ID (Preview)](https://learn.microsoft.com/en-us/entra/identity/conditional-access/agent-id)
- [Plan a Conditional Access deployment](https://learn.microsoft.com/en-us/entra/identity/conditional-access/plan-conditional-access)
