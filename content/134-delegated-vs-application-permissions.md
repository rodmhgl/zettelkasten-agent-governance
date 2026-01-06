# Delegated vs Application Permissions

#phase3 #access-control #permissions #scopes

## The Two Permission Types

Microsoft Graph (and other APIs) offers two permission models:

| Aspect | Delegated | Application |
|--------|-----------|-------------|
| **Also called** | Scopes | App roles |
| **User context** | ✅ Required | ❌ Not present |
| **Effective access** | Intersection of app + user permissions | App permissions only |
| **Consent** | User or admin | Admin only |
| **Use case** | Interactive agents | Autonomous agents |

## Delegated Permissions (Preferred)

Agent acts **on behalf of** a signed-in user:

```
Agent requests: Mail.Read
User has access to: Own mailbox + shared mailboxes
Agent can read: Only what user can read
```

**Benefits**:

- Natural least privilege (user's access bounds the agent)
- Clear audit trail (user + agent visible)
- User can revoke consent

## Application Permissions (Use Carefully)

Agent acts **as itself** with its own identity:

```
Agent has: Mail.Read (application)
Agent can read: ALL mailboxes in tenant
```

**When necessary**:

- Background processing without user present
- Cross-user operations (reporting, sync)
- System-level integrations

**Risks**:

- Over-privileged by default
- No user bounding
- Harder to audit intent

## Decision Framework

```
Is a user available during agent operation?
├── Yes → Use delegated permissions
└── No → 
    Does agent need cross-user access?
    ├── Yes → Application permissions (document carefully)
    └── No → Consider managed identity or service account
```

## Connection to Agent Operation Patterns

See [[102-entra-agent-id-overview]] for the two patterns:

- **Interactive agents** → Delegated permissions
- **Autonomous agents** → Application permissions

---

## Links

- [[130-least-privilege-agents]] - Why this choice matters
- [[102-entra-agent-id-overview]] - Interactive vs autonomous patterns

## Source

- [Overview of Microsoft Graph permissions](https://learn.microsoft.com/en-us/graph/permissions-overview)
- [Understanding delegated access](https://learn.microsoft.com/en-us/entra/identity-platform/delegated-access-primer)
- [Scopes and permissions in the Microsoft identity platform](https://learn.microsoft.com/en-us/entra/identity-platform/scopes-oidc)
