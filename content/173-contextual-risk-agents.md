---
title: 173-Contextual Risk - Agents Behaving Badly
tags:
  - concept
  - monitoring
  - risk-detection
---

## The Monitoring Challenge

Traditional security monitoring treats high-volume access patterns as breaches. For AI agents, that's just Tuesday.

Single identity reading thousands of documents + querying the entire directory + hitting multiple Graph endpoints = **red flag** for humans, **normal operation** for agents.

## Contextual vs. Binary Risk

| Traditional Approach | Contextual Approach |
|---------------------|---------------------|
| High volume = threat | High volume = expected for agent type |
| Anomaly = incident | Anomaly compared to agent baseline |
| Same rules for all | Rules adapted to identity category |

## What Agent ID Enables

Agents can be monitored as agents:

- High-volume patterns aren't automatically treated as breaches
- Risk assessment is contextual, not binary
- "Human doing something odd" separates from "AI doing exactly what it was designed to do"

## The Admin Benefit

Admins gain something they've been missing: the ability to say "Yes, this thing is weird—and that's okay, because we planned for it."

## Links

- [[140-agent-risk-detection]] - Risk signals for agents
- [[133-conditional-access-agents]] - Contextual policy enforcement
- [[170-identity-gap-ai-agents]] - Why traditional monitoring fails
- [[141-audit-reasoning-trace]] - Understanding agent behavior

## Source

[Mr.PlanB, "Entra Agent ID Explained: Microsoft's Attempt to Make AI Agents Safe Enough to Trust" (Medium, Dec 2025)](https://medium.com/@PlanB./entra-agent-id-explained-microsofts-attempt-to-make-ai-agents-safe-enough-to-trust-900a0975e43d)
