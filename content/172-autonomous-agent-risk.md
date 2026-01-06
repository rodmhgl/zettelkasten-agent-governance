---
title: 172-The Autonomous Agent Trust Problem
tags:
  - concept
  - security
  - risk
  - psychology
---

## The Psychological Line

Once something looks like a user, people treat it like one. They forget it doesn't think. It doesn't hesitate. It just executes.

Persistent autonomous agents that have mailboxes and Teams presence cross this psychological boundary.

## Why This Matters

Human users have friction:

- They read before clicking
- They hesitate on destructive actions
- They notice unusual requests
- They take breaks

Agents have none of these natural limits. A badly scoped agent can do damage faster than any human ever could.

## The Trust Paradox

Entra Agent ID doesn't make agents safe. It makes them governable.

- A badly scoped blueprint can still cause damage
- Application permissions still enable rapid data access
- Legitimate agent identities can still cause the first major "AI took down production" incident

## Microsoft's Position

Microsoft is framing Agent ID as an admin/security feature, not a developer tool. The goal isn't smarter agents—it's limiting blast radius when agents do something dumb, or exactly what you told them to do.

## Hard Limits

Microsoft has baked in restrictions:

- Agents cannot be assigned privileged Entra roles (non-negotiable)
- Clear signal that even Microsoft doesn't trust AI with admin access

## Links

- [[171-three-agent-identity-types]] - The persistent autonomous pattern
- [[142-automated-kill-switch]] - Rapid response to agent misbehavior  
- [[130-least-privilege-agents]] - Limiting what agents can do
- [[173-contextual-risk-agents]] - Separating "weird" from "bad"

## Source

[Mr.PlanB, "Entra Agent ID Explained: Microsoft's Attempt to Make AI Agents Safe Enough to Trust" (Medium, Dec 2025)](https://medium.com/@PlanB./entra-agent-id-explained-microsofts-attempt-to-make-ai-agents-safe-enough-to-trust-900a0975e43d)
