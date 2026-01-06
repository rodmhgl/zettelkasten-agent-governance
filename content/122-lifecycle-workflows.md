---
title: Lifecycle Workflows for Agents
tags:
  - phase2
  - governance
  - automation
  - lifecycle
---

## What Are Lifecycle Workflows?

Lifecycle Workflows (LCW) automate tasks at key moments in an identity's lifecycle:

- **Joiner**: When entering scope
- **Mover**: When changing roles/departments
- **Leaver**: When exiting scope

For agents, the critical use case is **sponsor mover/leaver handling**.

## The Problem

A human sponsor:

1. Changes departments (mover)
2. Leaves the company (leaver)
3. Goes on extended leave

Without automation, agents become "orphaned" - no one is accountable.

## Agent-Specific Tasks

Two built-in tasks for agent governance:

| Task | Trigger | Action |
|------|---------|--------|
| **Send email to manager about sponsorship changes** | Sponsor moves/leaves | Notify manager to reassign |
| **Send email to co-sponsors about sponsor changes** | Sponsor moves/leaves | Alert co-sponsors |

## Workflow Example

```
Trigger: Sponsor employee's department changes
Scope: All users who are sponsors of agent identities
Tasks:
  1. Send email to manager about sponsorship changes
  2. Send email to co-sponsors about sponsor changes
```

## Automatic Succession

When a sponsor leaves:

1. LCW detects the change
2. Notifications are sent
3. Sponsorship transfers to manager (if configured)
4. Agent always maintains accountability chain

---

## Links

- [[120-agent-sponsorship-model]] - Why sponsors matter
- [[121-owners-sponsors-managers]] - The three roles
- [[150-agent-decommissioning]] - When no sponsor can be found

## Source

- [Agent identity sponsor tasks in Lifecycle Workflows (Preview)](https://learn.microsoft.com/en-us/entra/id-governance/agent-sponsor-tasks)
- [What are lifecycle workflows?](https://learn.microsoft.com/en-us/entra/id-governance/what-are-lifecycle-workflows)
- [Lifecycle Workflow built-in tasks](https://learn.microsoft.com/en-us/entra/id-governance/lifecycle-workflow-tasks)
