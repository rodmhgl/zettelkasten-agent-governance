---
title: 100-Pets vs Swarms - Agent Management Paradigm
tags:
  - concept
  - governance
  - scalability
---

## The Shift

Traditional IT managed servers as "pets" - named, nurtured, manually configured. DevOps introduced "cattle" - numbered, automated, disposable.

AI agents require the same mental shift:

- **Pet agents**: Individually configured, manually tracked, bespoke permissions
- **Swarm agents**: Template-driven, policy-governed, automated lifecycle

## Why This Matters

Organizations deploying AI agents at scale cannot:

- Manually review each agent's permissions
- Track individual agent behavior without automation
- Respond to incidents on a per-agent basis

## The Solution

Apply governance to *types* of agents via [[110-agent-identity-blueprints]], not to individual instances. This enables:

- Consistent security posture across agent fleets
- Scalable policy enforcement
- Automated lifecycle management

---

## Links

- [[000-moc-agent-identity-governance]] - Parent MOC
- [[110-agent-identity-blueprints]] - How blueprints enable swarm management
- [[111-agent-registry]] - Central visibility for the swarm
- [[101-non-human-identity]] - The broader NHI context

## Source

Conceptual framework for Microsoft Entra Agent ID governance
