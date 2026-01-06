# Agent Sponsorship Model

#phase2 #governance #accountability #sponsor

## The Principle

**Every agent must have a human accountable for its actions.**

Unlike traditional service accounts that can exist without clear ownership, agent identities require explicit human sponsorship. This is a *required* field during creation.

## Why Sponsors Matter

Agents act autonomously. When things go wrong, someone must:
- Decide if behavior was expected
- Authorize suspension or permission changes
- Participate in security incident response
- Attest during access reviews

## Sponsor vs Owner vs Manager

See [[121-owners-sponsors-managers]] for the full comparison. Key distinction:

| Role | Focus | Permissions |
|------|-------|-------------|
| **Sponsor** | Business accountability | Lifecycle decisions, no tech admin |
| **Owner** | Technical administration | Config, credentials, settings |
| **Manager** | Organizational hierarchy | Request access packages |

## Sponsor Succession

When a sponsor leaves the organization:
1. Lifecycle Workflows detect the change (see [[122-lifecycle-workflows]])
2. Notifications sent to manager and co-sponsors
3. Sponsorship must be reassigned
4. **Agent is NOT orphaned**—always has accountability chain

## Groups as Sponsors

Both users and groups can be sponsors. When a group is assigned:
- All direct members have sponsor rights
- Enables team-based accountability
- Provides backup coverage

---

## Links

- [[121-owners-sponsors-managers]] - The three administrative roles
- [[122-lifecycle-workflows]] - Automating sponsor changes
- [[123-access-reviews-recertification]] - Sponsors attest to access

## Source

- [Administrative relationships in Microsoft Entra Agent ID (Owners, sponsors, and managers)](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/agent-owners-sponsors-managers)
- [Governing Agent Identities (Preview)](https://learn.microsoft.com/en-us/entra/id-governance/agent-id-governance-overview)
