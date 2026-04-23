---
name: upsell-sequencer
description: Design usage-triggered upsell / expansion sequences (in-app + email) that fire when a customer hits a plan boundary, usage milestone, or expansion-ready signal. Use when the user says "upsell sequence", "expansion revenue", "upgrade prompts", or is designing a higher tier.
status: new
---

# Upsell Sequencer (Revenue Squad)

Triggers expansion revenue from paid customers based on real usage signals — not calendar sends.

## Triggers

- "design upsell sequence"
- "expansion revenue flow"
- "upgrade prompts based on usage"
- "we launched a new tier — how do we move existing customers"

## Inputs required

1. **Plan boundary definitions** — seats, volume, feature-gate edges
2. **Plan ladder** — what's above the current plan, what's included
3. **Usage event data** — to fire triggers
4. **Existing customer segmentation** — plan, tenure, NPS, CSM assigned
5. **Trigger thresholds** — where does each signal fire

## Process

### Step 1 — Map expansion triggers

Catalog every signal that says "this customer is ready for more":

- **Usage-based** — approaching seat/volume limit (80%, 90%, 100%)
- **Feature-locked** — they tried to use a Business-tier feature on Pro
- **Value-realized** — hit N activations or milestones (happy = willing to pay more)
- **Team growth** — 2+ new users added in 30 days
- **Case study worthy** — NPS 9+ AND 90+ days retained

Each trigger fires its own sub-sequence.

### Step 2 — Design by trigger type

**Usage approaching limit:**

- Day 0 (80%): in-app banner "you're at 80% of your monthly quota"
- Day 3 (90% or still climbing): email "here's what you'll save on the annual Business plan"
- Day 7 (100%): hard gate + direct upgrade CTA + chat option

**Feature-locked:**

- In-product: locked feature modal with preview + "upgrade to unlock" CTA
- Email 3 days later if they haven't upgraded: "here's what that feature unlocks — a case study"

**Value-realized (happy signal):**

- Email: "you're in the top 20% of users. Teams at this usage level often upgrade to X for Y. Want to try free for 14 days?"

**Team growth:**

- In-app to admin: "your team grew from 3 → 5 seats. Pro charges per seat; Business is flat-rate past 10 — math attached."

### Step 3 — Write the copy

For every message:

- Lead with **value shown**, not feature listed
- Include **the math** — explicit saving or capability gain
- One CTA, one path, no branching

### Step 4 — Rules of the road

- Never upsell someone in their first 30 days (they haven't earned the right to be asked)
- Never upsell someone with an open support ticket > 48h
- Never upsell right after a pricing change — 60-day cool-off
- Cap: no more than 2 upsell messages in a 30-day window per customer

### Step 5 — Instrumentation + metrics

- `upsell_trigger_fired` (type, user_id, plan_from, plan_to)
- `upsell_cta_clicked`
- `upsell_converted`
- `expansion_arr`

Primary metric: **expansion MRR from this flow**.
Guardrails: churn rate in users who received upsells, unsubscribe rate.

## Output artifact

`upsell-sequences.md` with:

- Trigger catalog
- Per-trigger flow + copy
- Rules of the road
- Metrics spec
- Hypothesis per sequence

## Handoff

- In-app → product
- Emails → Lifecycle Email Designer
- Expansion ARR → Revenue Dashboard Builder
- Hypotheses → A/B Test Designer

## Example call

> "Build our upsell sequences. We have Pro ($29/seat) → Business ($99/flat up to 25 seats, then custom). Trigger on 80% seat utilization and when team hits 10+ seats. Usage data in events.csv."
