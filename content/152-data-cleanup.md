---
title: 152-Data Cleanup for Retired Agents
tags:
  - phase5
  - retirement
  - data
  - privacy
---

## The Challenge

Revoking an agent's identity doesn't remove the data it accumulated:

- Conversation history / memory
- Cached documents
- Learned preferences
- Generated artifacts
- Vector embeddings
- Local state

This data can leak sensitive information if not properly handled.

## Data Categories

| Category | Location | Cleanup Method |
|----------|----------|----------------|
| **Identity metadata** | Entra ID | Soft/hard delete |
| **Conversation memory** | Agent platform (Copilot Studio, etc.) | Platform-specific |
| **Document cache** | Agent storage | Delete container/bucket |
| **Vector embeddings** | AI Search, Pinecone, etc. | Delete index or filter |
| **Audit logs** | Log Analytics, SIEM | Retain per policy |
| **Generated files** | SharePoint, OneDrive | Archive or delete |

## Cleanup Process

```
1. Inventory agent data stores
   └── Where does/did the agent store data?

2. Classify by retention requirement
   └── Audit logs: Retain 7 years
   └── PII cache: Delete immediately
   └── Business artifacts: Archive

3. Execute cleanup per store
   └── Platform-specific procedures

4. Verify cleanup
   └── Confirm data is inaccessible

5. Document for compliance
   └── Record what was deleted when
```

## Memory/Conversation Cleanup

For agents with persistent memory:

- Delete conversation threads
- Clear user preference storage
- Remove learned context
- Purge RAG index entries specific to this agent

## Compliance Considerations

| Regulation | Requirement |
|------------|-------------|
| **GDPR** | Right to erasure includes agent-held data |
| **CCPA** | Deletion requests apply to agent caches |
| **SOX** | Audit logs must be retained regardless |
| **HIPAA** | PHI in agent memory requires secure deletion |

## Platform-Specific Guidance

Each agent hosting platform has different cleanup mechanisms:

- **Copilot Studio**: Conversation history deletion via admin center
- **Azure AI Agent Service**: Storage account lifecycle policies
- **Custom agents**: Application-specific cleanup scripts

---

## Links

- [[150-agent-decommissioning]] - Overall retirement process
- [[151-credential-revocation]] - Before data cleanup
- [[141-audit-reasoning-trace]] - Logs retained for compliance

## Source

- [Governing Microsoft Entra service accounts - Deprovisioning](https://learn.microsoft.com/en-us/entra/architecture/govern-service-accounts#build-a-lifecycle-process)
- Platform-specific documentation for data lifecycle management
