---
title: Microsoft Entra Agent ID Overview
tags:
  - platform
  - entra
  - agent-id
---

## What It Is

Microsoft Entra Agent ID is an identity and authorization framework purpose-built for AI agents. Unlike traditional application identities (service principals) or user identities, Agent ID addresses the unique challenges of autonomous AI systems.

## Core Components

| Component | Purpose |
|-----------|---------|
| **Agent Identity Blueprint** | Template defining agent type, shared config |
| **Agent Identity** | Primary authentication account for an agent instance |
| **Agent User** | Optional user-like account for systems requiring user objects |
| **Agent Registry** | Centralized metadata repository and discovery service |

## Key Differentiators from Service Principals

1. **Blueprints**: Policy applies to *types* of agents, not just instances
2. **Sponsors**: Built-in human accountability model
3. **No passwords**: Agents authenticate via tokens from their hosting platform
4. **Registry**: Centralized discovery and inventory

## Two Operation Patterns

1. **Interactive/Delegated**: Agent acts on behalf of a signed-in user
2. **Autonomous**: Agent acts under its own identity

See [[134-delegated-vs-application-permissions]] for choosing between these.

---

## Links

- [[110-agent-identity-blueprints]] - Deep dive on blueprints
- [[111-agent-registry]] - The centralized inventory
- [[121-owners-sponsors-managers]] - The accountability model

## Source

- [What is Microsoft agent identity platform](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/what-is-agent-id-platform)
- [What are agent identities](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/what-is-agent-id)

## Status

⚠️ **Preview** - Part of Microsoft Agent 365 (Frontier early access program)
