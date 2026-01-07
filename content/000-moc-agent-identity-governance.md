---
title: 000-Agent Identity Governance - Map of Content
tags:
  - moc
  - agent-governance
  - entra
  - nhi
---

## Overview

This MOC connects notes about governing AI agent identities at enterprise scale using Microsoft Entra Agent ID. The framework transitions organizations from managing individual "pet" agents to scalable "swarm" governance.

---

## Core Concepts

- [[100-pets-vs-swarms]] - The paradigm shift in agent management
- [[101-non-human-identity]] - What NHI means for security teams
- [[102-entra-agent-id-overview]] - Microsoft's agent identity platform

---

## Lifecycle Phases

### Phase 1: Registration & Discovery

- [[110-agent-identity-blueprints]] - Templates for agent types
- [[111-agent-registry]] - Centralized inventory
- [[112-unique-machine-identities]] - One identity per agent
- [[113-autonomy-classification]] - Risk-based tiering

### Phase 2: Ownership & Sponsorship

- [[120-agent-sponsorship-model]] - Human accountability
- [[121-owners-sponsors-managers]] - The three roles
- [[122-lifecycle-workflows]] - Mover/leaver automation
- [[123-access-reviews-recertification]] - Periodic attestation

### Phase 3: Access Control

- [[130-least-privilege-agents]] - Never permanent, never broad
- [[131-access-packages]] - Bundled permissions
- [[132-time-bound-access]] - Expiration policies
- [[133-conditional-access-agents]] - Policy-based controls
- [[134-delegated-vs-application-permissions]] - Scope decisions

### Phase 4: Monitoring & Protection

- [[140-agent-risk-detection]] - Anomaly monitoring
- [[141-audit-reasoning-trace]] - The "why" not just "what"
- [[142-automated-kill-switch]] - Risk-triggered revocation

### Phase 5: Retirement

- [[150-agent-decommissioning]] - End-of-life process
- [[151-credential-revocation]] - Disabling access
- [[152-data-cleanup]] - Memory and cache handling

---

## Implementation Patterns

- [[160-zero-trust-agents]] - Trust nothing, verify everything
- [[161-agent-conditional-access-policies]] - Common CA patterns

---

## Sources

Primary:

- [YouTube - BRK265 - Secure access for AI agents with Microsoft Entra](https://www.youtube.com/watch?v=rBRwT0E0jQA)
- [Ignite - BRK265 - Secure access for AI agents with Microsoft Entra](https://ignite.microsoft.com/en-US/sessions/BRK265)

Updated: January 2026
