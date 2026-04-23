# 📣 Referral Squad

**Mission:** Turn happy customers into distribution. Build the flywheel.

**North-star metric:** % of new customers acquired via referral or advocacy.
**Guardrails:** Referral program CAC < 30% of paid CAC.

## Agents in this squad

| Agent | Upstream | What it produces |
|---|---|---|
| [referral-program-designer](./referral-program-designer/SKILL.md) | **new** | Program mechanics + incentive math + tracking spec |
| [case-study-builder](./case-study-builder/SKILL.md) | **new** | Publish-ready case study from interview |
| [advocate-identifier](./advocate-identifier/SKILL.md) | **new** | Ranked advocate list with outreach-ready messages |

## Typical chain

```
advocate-identifier (finds champions)
        ↓
case-study-builder (captures their story)
        ↓
referral-program-designer (gives them a lever)
```

## Handoff contract back to Acquisition

Referral produces:
- Case study assets → Acquisition's landing pages + paid ads
- Referral-sourced leads → Welcome Sequencer (tagged `source=referral`)
- Advocate quotes → Competitive Scout's battlecards
