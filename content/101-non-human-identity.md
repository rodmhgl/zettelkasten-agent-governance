# Non-Human Identity (NHI)

#concept #identity #security

## Definition

Non-human identities (NHI) are any identity not associated with a human user. In Microsoft Entra, these include:

- **Workload identities**: Applications, service principals, managed identities
- **Agent identities**: AI agents with autonomous capabilities
- **Device identities**: Computers, IoT sensors, managed devices

## The Security Gap

Most IAM solutions focus on human identities. NHIs present unique challenges:

1. **Volume**: NHIs often outnumber human identities 10:1 or more
2. **Credentials**: May use certificates, secrets, or federated credentials—not passwords
3. **Lifecycle**: Created/destroyed programmatically, not through HR processes
4. **Behavior**: Actions may appear anomalous by human standards

## Agent Identities as NHI

AI agents are a *subset* of NHI with additional complexity:
- May act autonomously OR on behalf of users
- Require "reasoning trace" auditing (see [[141-audit-reasoning-trace]])
- Need human sponsors for accountability (see [[120-agent-sponsorship-model]])

---

## Links

- [[102-entra-agent-id-overview]] - Microsoft's solution for agent NHI
- [[112-unique-machine-identities]] - Why each agent needs its own identity
- [[140-agent-risk-detection]] - Detecting anomalous NHI behavior

## Source

- [What are workload identities?](https://learn.microsoft.com/en-us/entra/workload-id/workload-identities-overview)
- [Microsoft Entra fundamentals - Terminology](https://learn.microsoft.com/en-us/entra/architecture/secure-fundamentals#terminology)
