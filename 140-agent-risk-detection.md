# Agent Risk Detection

#phase4 #monitoring #risk #identity-protection

## What It Is

ID Protection for agents continuously evaluates agent behavior and assigns risk scores based on anomalies. Unlike signature-based detection, it uses ML to identify deviations from baseline behavior.

## Risk Detection Types for Agents

| Detection | Description | Severity |
|-----------|-------------|----------|
| **Unfamiliar resource access** | Agent targets resources it doesn't usually access | Medium-High |
| **Sign-in spike** | Abnormal authentication frequency | Medium |
| **Failed access attempt** | Repeated unauthorized resource attempts | Medium |
| **Sign-in by risky user** | Delegated auth with compromised user | High |
| **Confirmed compromised** | Admin-confirmed compromise | Critical |
| **Threat intelligence** | Matches known attack patterns | High |

## Risk Levels

Agents are classified into risk levels:
- **None**: Normal behavior
- **Low**: Minor anomalies
- **Medium**: Suspicious patterns
- **High**: Likely compromise

## Connection to Conditional Access

Risk scores feed directly into [[133-conditional-access-agents]]:

```
IF agent_risk = High
THEN Block access
     Notify sponsor
     Revoke tokens
```

## Monitoring Setup

1. Enable ID Protection for agents (preview)
2. Configure risk thresholds
3. Create CA policies for risk-based blocking
4. Set up alerts for sponsor notification

## Comparison to Workload Identity Risk

Agent risk detection builds on workload identity risk but adds:
- Agent-specific anomalies (reasoning patterns)
- Blueprint-level baselines
- Integration with agent registry

---

## Links

- [[133-conditional-access-agents]] - Risk-based policy enforcement
- [[142-automated-kill-switch]] - Automatic response to high risk
- [[141-audit-reasoning-trace]] - Investigating anomalies

## Source

- [ID Protection for agents (Preview)](https://learn.microsoft.com/en-us/entra/id-protection/concept-risky-agents)
- [Securing workload identities](https://learn.microsoft.com/en-us/entra/id-protection/concept-workload-identity-risk)
- [What are risk detections?](https://learn.microsoft.com/en-us/entra/id-protection/concept-identity-protection-risks)
