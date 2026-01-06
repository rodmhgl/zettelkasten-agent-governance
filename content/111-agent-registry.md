# Agent Registry

#phase1 #registration #inventory #discovery

## What It Is

The Agent Registry is a **centralized metadata repository** that maintains information about all registered agents in an organization. It serves as both:

1. **Inventory**: Complete catalog of deployed agents
2. **Discovery service**: Enables agent-to-agent communication

## Why Centralization Matters

Without a registry, organizations face:

- Shadow agents deployed without IT knowledge
- No visibility into third-party vendor agents
- Inability to apply consistent policies
- No way to audit the agent population

## Key Capabilities

| Capability | Benefit |
|------------|---------|
| Comprehensive inventory | Track ALL agents, including external |
| Discovery policies | Control which agents can find each other |
| Collections | Group agents for policy enforcement |
| Rich metadata | Capture agent purpose, skills, capabilities |

## Collections

Agents are organized into **collections** with discovery policies:

- **Global Collection**: All agents, discoverable by default
- **Custom Collections**: Admin-defined, scoped discovery

This enables Zero Trust principles for agent communication.

## Registration Methods

1. **Automatic**: Microsoft platforms (Copilot Studio, etc.) auto-register
2. **Self-serve**: Non-Microsoft agents via Microsoft Graph API

---

## Links

- [[100-pets-vs-swarms]] - Registry enables swarm visibility
- [[110-agent-identity-blueprints]] - Blueprints define what gets registered
- [[160-zero-trust-agents]] - Registry enforces trust boundaries

## Source

- [What is the Microsoft Entra Agent Registry?](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/what-is-agent-registry)
- [Register agents to the Agent Registry](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/publish-agents-to-registry)
- [Agent Registry collections](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/agent-registry-collections)
