# 🔁 Retention Squad

**Mission:** Keep users engaged past activation. Reduce churn. Spot expansion triggers.

**North-star metric:** Net revenue retention (NRR). Secondary: D30 / W12 retention curves.
**Guardrails:** Gross churn < 5%/mo (SMB) or < 1%/mo (mid-market).

## Agents in this squad

| Agent | Upstream | What it produces |
|---|---|---|
| [lifecycle-email-designer](./lifecycle-email-designer/SKILL.md) | `marketing:email-sequence` | Ongoing drip + milestone emails |
| [cohort-churn-analyzer](./cohort-churn-analyzer/SKILL.md) | **new** | Cohort curves + churn-driver table |
| [nps-synthesizer](./nps-synthesizer/SKILL.md) | `design:research-synthesis` | NPS themes, segments, action list |
| [reengagement-campaigner](./reengagement-campaigner/SKILL.md) | **new** | Dormant-user win-back flow |
| [feature-adoption-tracker](./feature-adoption-tracker/SKILL.md) | **new** | Adoption heatmap + nudge queue |

## Typical chain

```
cohort-churn-analyzer (finds where users drop)
        ↓
nps-synthesizer (finds why users drop)
        ↓
feature-adoption-tracker (finds which features prevent drop)
        ↓
lifecycle-email-designer + reengagement-campaigner
```

## Handoff contract to Revenue

Retention flags users to Revenue when:
- Usage crosses an upgrade threshold (team size, volume, features)
- NPS ≥ 9 (candidate for upsell + case study)
- Engagement pattern matches "expansion-ready" profile
