# Access Reviews for Agent Recertification

#phase2 #governance #attestation #compliance

## The Principle

Permissions granted to agents should be **periodically validated**. Sponsors must explicitly confirm that an agent still requires its access.

## Why Recertification Matters

- Projects end but permissions persist
- Business needs change
- Scope creep accumulates permissions over time
- Compliance requires evidence of review

## Access Review Mechanics

| Setting | Recommendation for Agents |
|---------|---------------------------|
| **Frequency** | Quarterly minimum for action-oriented agents |
| **Reviewers** | Sponsor (primary), Manager (fallback) |
| **Duration** | 14-30 days to allow business review |
| **If no response** | Remove access (conservative default) |

## Multi-Stage Reviews

For high-risk agents, use multi-stage reviews:

```
Stage 1: Sponsor confirms business need
Stage 2: Security team validates permissions
Stage 3: Final approval if both agree
```

This ensures consensus without overwhelming single reviewers.

## Review Scope Options

- **Group membership**: Does agent need this group?
- **Application access**: Does agent need this app?
- **Access package assignments**: Does agent need this bundle?
- **Role assignments**: Does agent need this role?

## Recommendations Engine

Microsoft Entra provides ML-based recommendations:

- Flag inactive agents
- Identify excessive permissions
- Detect low user-to-group affiliation

---

## Links

- [[120-agent-sponsorship-model]] - Sponsors as primary reviewers
- [[131-access-packages]] - What gets reviewed
- [[132-time-bound-access]] - Expiration as complement to reviews

## Source

- [Plan a Microsoft Entra access reviews deployment](https://learn.microsoft.com/en-us/entra/id-governance/deploy-access-reviews)
- [Manage user and guest user access with access reviews](https://learn.microsoft.com/en-us/entra/id-governance/manage-access-review)
- [Using multi-stage reviews](https://learn.microsoft.com/en-us/entra/id-governance/using-multi-stage-reviews)
