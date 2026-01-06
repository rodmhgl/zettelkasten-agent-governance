---
title: Agent Autonomy Classification
tags:
  - phase1
  - registration
  - risk
  - classification
---

## Why Classify?

Not all agents are equal. A read-only reporting agent poses different risks than an agent that can execute financial transactions. Classification enables **tiered security controls**.

## Classification Dimensions

### By Capability

| Level | Description | Example |
|-------|-------------|---------|
| **Read-only** | Can query but not modify | Dashboard reporter |
| **Action-oriented** | Can create/update/delete | Sales automation |
| **Administrative** | Can modify configurations | IT ops agent |

### By Risk Level

| Risk | Criteria | Controls |
|------|----------|----------|
| **Low** | Internal data, limited scope | Standard CA |
| **Medium** | PII, business-critical | Enhanced monitoring |
| **High** | Financial, regulatory, admin | MFA, approval workflows |

## Using Collections for Classification

The [[111-agent-registry]] supports **collections** for grouping:

- Create collections by risk tier
- Apply discovery policies per collection
- Scope CA policies to collections

## Connection to Conditional Access

Classification feeds into [[133-conditional-access-agents]]:

- "High-risk agents require compliant device"
- "Read-only agents allowed from any network"
- "Admin agents blocked if risk score elevated"

---

## Links

- [[110-agent-identity-blueprints]] - Classification at the blueprint level
- [[111-agent-registry]] - Collections for grouping
- [[133-conditional-access-agents]] - Policy enforcement
- [[140-agent-risk-detection]] - Runtime risk assessment

## Source

- [Agent Registry collections](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/agent-registry-collections)
- [Security for AI agents with Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/identity-professional/security-for-ai)
