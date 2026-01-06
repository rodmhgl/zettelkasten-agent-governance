---
title: 171-Three Agent Identity Patterns
tags:
  - concept
  - entra
  - agent-id
  - architecture
---

## The Framework

Microsoft Entra Agent ID isn't a single identity type. It explicitly supports three distinct patterns, each with different trust implications.

## On-Behalf-Of Agent

Acts as a user with delegated permissions within blueprint boundaries.

- Closest to traditional delegated access
- User's permissions constrain actions
- Agent inherits user context

**Use case**: Copilot-style assistants that help users with their own data.

## Ephemeral Agent Identity

Short-lived identities spun up for a task, then discarded.

- No long-lived secrets
- No permanent service principal accumulating permissions
- Solves the credential sprawl problem admins have been patching for years

**Use case**: Task-specific automation, on-demand processing, CI/CD-style agent workflows.

## Persistent Autonomous Agent

Agents that operate as themselves, not on behalf of any user.

- Can have mailboxes
- Can appear in Teams
- Can interact with SharePoint directly
- Most powerful—and most concerning

**Use case**: Customer service agents, autonomous business process automation.

## Risk Comparison

| Type | Risk Level | Key Control |
|------|------------|-------------|
| On-behalf-of | Lower | User permissions bound scope |
| Ephemeral | Medium | No persistence limits blast radius |
| Persistent autonomous | Higher | Requires strongest governance |

## Links

- [[170-identity-gap-ai-agents]] - Why three types emerged
- [[110-agent-identity-blueprints]] - How blueprints govern all three types
- [[172-autonomous-agent-risk]] - The psychological line with persistent agents
- [[134-delegated-vs-application-permissions]] - Permission model choices

## Source

[Mr.PlanB, "Entra Agent ID Explained: Microsoft's Attempt to Make AI Agents Safe Enough to Trust" (Medium, Dec 2025)](https://medium.com/@PlanB./entra-agent-id-explained-microsofts-attempt-to-make-ai-agents-safe-enough-to-trust-900a0975e43d)
