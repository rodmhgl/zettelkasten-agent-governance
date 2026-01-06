---
title: 170-AI Agents - The Identity Model Gap
tags:
  - concept
  - governance
  - security
---

## The Problem

Traditional identity constructs in Microsoft Entra ID—app registrations, managed identities, service principals—were designed for background automation: scheduled tasks, daemons, silent jobs.

AI agents break these assumptions because they:

- Read massive volumes of data in minutes
- Chain API calls across multiple endpoints
- Act on behalf of users dynamically
- Exhibit behavior patterns that mimic compromised accounts

From a security perspective, an agent querying thousands of documents and hitting multiple Graph endpoints looks identical to credential theft or lateral movement.

## Why Traditional Models Fail

| Model | Limitation for Agents |
| ------- | ---------------------- |
| Service Principals | Powerful but blunt; no behavioral context |
| Delegated Permissions | Assumes human behind the keyboard |
| Conditional Access | Barely applies to workloads |
| MFA | No human to authenticate |

## The Recognition

Microsoft is drawing a new line: AI agents aren't apps, and they're not users. They occupy a new category requiring purpose-built identity primitives.

## Links

- [[102-entra-agent-id-overview]] - Microsoft's response to this gap
- [[101-non-human-identity]] - The broader NHI context
- [[171-three-agent-identity-types]] - The identity patterns that address this gap
- [[140-agent-risk-detection]] - Contextual risk vs. binary threat detection

## Source

[Mr.PlanB, "Entra Agent ID Explained: Microsoft's Attempt to Make AI Agents Safe Enough to Trust" (Medium, Dec 2025)](https://medium.com/@PlanB./entra-agent-id-explained-microsofts-attempt-to-make-ai-agents-safe-enough-to-trust-900a0975e43d)
