# Automated Kill Switch

#phase4 #monitoring #response #revocation

## The Principle

When an agent's risk score exceeds a threshold, access should be **automatically revoked** without waiting for human intervention. Speed matters—compromised agents can act at machine speed.

## Kill Switch Components

A complete kill switch requires:

1. **Detection**: Risk signal from ID Protection
2. **Decision**: CA policy evaluating risk
3. **Enforcement**: Token revocation and access block
4. **Notification**: Alert to sponsor and security team

## Implementation via Conditional Access

```
Policy: Agent Kill Switch
Conditions:
  - Agent identities: All
  - Agent risk: High or Critical
Grant controls:
  - Block access
Session controls:
  - Revoke refresh tokens immediately
```

## Revocation Methods

| Method | Speed | Scope |
|--------|-------|-------|
| **CA block** | Next auth attempt | New requests only |
| **Token revocation** | Minutes | Active sessions |
| **Disable agent identity** | Immediate | All access |
| **Delete agent identity** | Immediate | Permanent (use carefully) |

## Escalation Path

```
Risk detected
├── Low → Log only, monitor
├── Medium → Alert sponsor, require re-auth
├── High → Block new access, revoke tokens
└── Critical → Disable identity, notify SOC
```

## Manual Kill Switch

Sometimes humans need to trigger immediately:
- Security incident response
- Suspected compromise
- Emergency change freeze

Disabling via portal or Graph API:
```http
PATCH /agents/{id}
{
  "accountEnabled": false
}
```

---

## Links

- [[140-agent-risk-detection]] - Risk signals trigger kill switch
- [[133-conditional-access-agents]] - Policy enforcement mechanism
- [[151-credential-revocation]] - Permanent disabling

## Source

- [Disable agent identities in your tenant](https://learn.microsoft.com/en-us/entra/agent-id/identity-professional/disable-agent-identities)
- [How to investigate risk](https://learn.microsoft.com/en-us/entra/id-protection/howto-identity-protection-investigate-risk)
- [Revoke user access in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/users/users-revoke-access)
