---
title: Agent Decommissioning
tags:
  - phase5
  - retirement
  - lifecycle
  - cleanup
---

## The Principle

**Agent identities should not outlive their usefulness.**

When a project ends, team disbands, or agent is replaced, the identity must be formally retired - not abandoned.

## Decommissioning Triggers

| Trigger | Detection Method |
|---------|------------------|
| Project completion | Manual process or project management integration |
| Access package expiration | Automatic via entitlement management |
| Failed access review | Sponsor non-response triggers removal |
| Sponsor departure | Lifecycle Workflow with no successor |
| Security incident | Kill switch activation (see [[142-automated-kill-switch]]) |
| Budget/cost optimization | Periodic NHI review |

## Decommissioning Steps

```
1. Disable authentication
   └── accountEnabled = false

2. Revoke active tokens
   └── Continuous Access Evaluation (CAE)

3. Remove permissions
   └── Group memberships, app roles, API permissions

4. Archive audit logs
   └── Retain for compliance period

5. Data cleanup
   └── See [[152-data-cleanup]]

6. Soft delete identity
   └── 30-day recovery window

7. Hard delete (optional)
   └── Permanent removal after recovery period
```

## Soft Delete vs Hard Delete

| State | Can Recover? | Visible in Portal? | Tokens Valid? |
|-------|--------------|-------------------|---------------|
| Disabled | Yes | Yes | No |
| Soft deleted | 30 days | Deleted items only | No |
| Hard deleted | No | No | No |

**Recommendation**: Soft delete first, hard delete only after compliance retention period.

## Automation Options

- **Access package expiration**: Auto-remove after N days
- **Lifecycle Workflows**: Trigger on sponsor departure
- **Scheduled reviews**: Identify inactive agents
- **Graph API automation**: Custom decommissioning pipelines

---

## Links

- [[122-lifecycle-workflows]] - Automated triggers
- [[132-time-bound-access]] - Expiration as soft decommission
- [[151-credential-revocation]] - Disabling access
- [[152-data-cleanup]] - Handling agent data

## Source

- [Governing Microsoft Entra service accounts](https://learn.microsoft.com/en-us/entra/architecture/govern-service-accounts)
- [Disable user sign-in for an application](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/disable-user-sign-in-portal)
- [Remove unused credentials from apps](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/recommendation-remove-unused-credential-from-apps)
