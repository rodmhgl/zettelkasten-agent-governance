# Time-Bound Access for Agents

#phase3 #access-control #expiration #temporal

## The Principle

**Access should expire automatically unless explicitly renewed.**

No agent should have permanent permissions. Expiration forces periodic review and prevents permission accumulation.

## Expiration Strategies

| Strategy | Use Case | Typical Duration |
|----------|----------|------------------|
| **Fixed date** | Project-based agents | Project end date |
| **Number of days** | Standard operational agents | 90-180 days |
| **Number of hours** | Sensitive/emergency access | 4-8 hours |
| **Never** | ❌ Avoid for agents | N/A |

## Configuration Layers

Expiration can be set at multiple levels:

```
Access Package Policy
└── Expiration: 180 days
    └── PIM Group Assignment
        └── Expire eligible after: 90 days
            └── Conditional Access Session
                └── Sign-in frequency: 24 hours
```

**Important**: The most restrictive wins. If access package allows 180 days but PIM expires in 90, access ends at 90.

## Renewal Workflows

When expiration approaches:
1. **14 days before**: Email notification to agent's manager
2. **1 day before**: Final reminder
3. **On expiration**: Access removed automatically
4. **Extension request**: Requires justification and approval

## Complementary Controls

Time-bound access works alongside:
- [[123-access-reviews-recertification]] - Periodic human attestation
- [[142-automated-kill-switch]] - Immediate revocation on risk
- [[133-conditional-access-agents]] - Session lifetime controls

---

## Links

- [[131-access-packages]] - Where expiration is configured
- [[123-access-reviews-recertification]] - Complementary control
- [[150-agent-decommissioning]] - Expiration as soft decommission

## Source

- [Change lifecycle settings for an access package](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-access-package-lifecycle-policy)
- [Create an access review of an access package](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-access-reviews-create)
- [Using groups managed by PIM with access packages](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-access-package-pim-reference)
