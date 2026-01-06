# Credential Revocation for Agents

#phase5 #retirement #credentials #security

## The Challenge

Agent identities may have multiple credential types:

- Federated identity credentials (from hosting platform)
- Certificates (for legacy integrations)
- Client secrets (avoid, but may exist)

All must be addressed during decommissioning.

## Credential Types and Revocation

| Credential Type | Revocation Method | Time to Effect |
|-----------------|-------------------|----------------|
| **Federated** | Remove trust relationship | Immediate |
| **Certificate** | Remove from app registration | Next auth |
| **Client secret** | Delete secret | Next auth |
| **Refresh token** | Revoke via Graph API | Minutes (CAE) |
| **Access token** | Wait for expiry OR revoke | 1 hour max |

## Federated Credentials (Preferred)

Agent identities use **federated identity credentials** - no passwords or secrets stored in Entra. The hosting platform (Copilot Studio, Azure AI, etc.) issues tokens that Entra trusts.

Revocation: Remove the federated credential configuration.

```http
DELETE /applications/{appId}/federatedIdentityCredentials/{id}
```

## Continuous Access Evaluation (CAE)

CAE ensures revocation takes effect quickly:

- Tokens are evaluated continuously, not just at issuance
- Critical events (disable, revoke) propagate in minutes
- Supported by Microsoft 365 and Azure services

## Revocation Checklist

```
☐ Disable agent identity (accountEnabled = false)
☐ Revoke refresh tokens
☐ Remove federated identity credentials
☐ Delete any certificates
☐ Delete any client secrets
☐ Remove from all groups
☐ Remove application role assignments
☐ Remove API permission grants
☐ Verify no active sessions remain
```

## PowerShell Example

```powershell
# Revoke all tokens for an agent
Revoke-MgUserSignInSession -UserId <agent-user-id>

# Remove service principal
Remove-MgServicePrincipal -ServicePrincipalId <sp-id>
```

---

## Links

- [[150-agent-decommissioning]] - Overall retirement process
- [[142-automated-kill-switch]] - Emergency revocation
- [[152-data-cleanup]] - After credentials are revoked

## Source

- [Grant and revoke API permissions](https://learn.microsoft.com/en-us/powershell/microsoftgraph/how-to-grant-revoke-api-permissions)
- [Remove-EntraServicePrincipal](https://learn.microsoft.com/en-us/powershell/module/microsoft.entra.applications/remove-entraserviceprincipal)
- [Revoke user access in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/users/users-revoke-access)
