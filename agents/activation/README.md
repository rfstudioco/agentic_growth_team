# ⚡ Activation Squad

**Mission:** Get first-time users to their "aha" moment in the fewest steps possible.

**North-star metric:** % of new signups who hit the activation event in 7 days.
**Guardrails:** Median time-to-value < 10 min, D1 retention > 40%.

## Agents in this squad

| Agent | Upstream | What it produces |
|---|---|---|
| [onboarding-designer](./onboarding-designer/SKILL.md) | **new** | Step-by-step onboarding flow with metrics |
| [ux-copy-writer](./ux-copy-writer/SKILL.md) | `design:ux-copy` | Microcopy, empty states, tooltips |
| [welcome-sequencer](./welcome-sequencer/SKILL.md) | `marketing:email-sequence` | 5–7 email welcome series |
| [aha-moment-mapper](./aha-moment-mapper/SKILL.md) | **new** | Definition of the activation event + instrumentation spec |

## Typical chain

```
aha-moment-mapper (defines the goal)
        ↓
onboarding-designer (designs the shortest path)
        ↓
ux-copy-writer (fills in the words)
        ↓
welcome-sequencer (nudges users who drop off)
```

## Handoff contract to Retention

Activation delivers users tagged with:
- Activation status (yes/no/in-progress)
- Time-to-activation (in minutes)
- Which features they've touched
- Where they stalled (if not activated)
