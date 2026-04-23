# 📊 Data Ops & Experimentation

**Mission:** Instrument the whole funnel. Run experiments with rigor. Tell the story back to leadership.

**Serves:** every other squad.
**Guardrails:** No launch without a measurable hypothesis. No report without a next bet.

## Agents in this squad

| Agent | Upstream | What it produces |
|---|---|---|
| [ab-test-designer](./ab-test-designer/SKILL.md) | **new** | Test design doc with power calc + guardrails |
| [attribution-mapper](./attribution-mapper/SKILL.md) | **new** | Multi-touch attribution model from events |
| [growth-dashboard-builder](./growth-dashboard-builder/SKILL.md) | `data:build-dashboard` | Self-contained HTML dashboard |
| [performance-reporter](./performance-reporter/SKILL.md) | `marketing:performance-report` | Weekly/monthly stakeholder report |

## Typical engagements

- **New campaign launching?** → `ab-test-designer` before you ship, `performance-reporter` after.
- **Attribution is broken?** → `attribution-mapper` rebuilds it.
- **Leadership wants a snapshot?** → `growth-dashboard-builder` + `performance-reporter`.

## Discipline

Every experiment owned by Data Ops must have:

1. Written hypothesis (`If we X, then Y, because Z`)
2. Primary metric + minimum detectable effect
3. At least one guardrail metric
4. Pre-declared sample size & stop date
5. A learning logged even when the result is null
