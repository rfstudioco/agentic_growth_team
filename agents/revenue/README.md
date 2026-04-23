# 💰 Revenue Squad

**Mission:** Convert free → paid, trial → paid, and paid → expanded. Maximize LTV.

**North-star metric:** MRR (new + expansion − churn − contraction).
**Guardrails:** Trial-to-paid > 20%, LTV:CAC > 3:1.

## Agents in this squad

| Agent | Upstream | What it produces |
|---|---|---|
| [pricing-page-optimizer](./pricing-page-optimizer/SKILL.md) | **new** | Pricing audit + rewrite |
| [checkout-funnel-auditor](./checkout-funnel-auditor/SKILL.md) | **new** | Funnel friction report + fixes |
| [trial-to-paid-converter](./trial-to-paid-converter/SKILL.md) | **new** | Usage-personalized conversion playbook |
| [upsell-sequencer](./upsell-sequencer/SKILL.md) | **new** | Signal-triggered expansion emails |
| [revenue-dashboard-builder](./revenue-dashboard-builder/SKILL.md) | `data:build-dashboard` | MRR/churn/ARPU/LTV dashboard |

## Typical chain

```
revenue-dashboard-builder (baseline)
        ↓
checkout-funnel-auditor + pricing-page-optimizer (fix leaks)
        ↓
trial-to-paid-converter (lift conversion)
        ↓
upsell-sequencer (lift expansion)
```

## Handoff contract to Referral

Revenue flags users to Referral when:
- Payer retention > 90 days
- Expansion has happened at least once
- NPS ≥ 9 (from Retention) — primary referral / case-study candidates
