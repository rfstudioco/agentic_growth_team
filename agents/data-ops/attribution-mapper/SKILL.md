---
name: attribution-mapper
description: Build a multi-touch attribution model from raw event data — touch journeys, model comparison (first / last / linear / position / time-decay), and channel-level ROI. Use when the user says "fix our attribution", "build an attribution model", "which channels drive signups", or "why does GA say one thing and Facebook another".
status: new
---

# Attribution Mapper (Data Ops)

Builds a transparent, explainable attribution model from raw events. Optimized for "good enough to make decisions" over "perfect but nobody understands".

## Triggers

- "fix our attribution"
- "build a multi-touch attribution model"
- "which channels actually drive signups / revenue"
- "why does GA say X and Meta Ads Manager say Y"
- "how do I credit channels for conversions"

## Inputs required

1. **Touch events** — timestamps, user/session ID, channel, campaign, source, medium
2. **Conversion events** — signup, activation, paid conversion (map to Aha-Moment Mapper + Revenue)
3. **Attribution window** — how far back to look (default: 30 days for signup, 90 for paid)
4. **Cross-device identity** — do we have logged-in resolution? If no, flag the gap
5. **Current vendor tools** — GA4, Segment, Amplitude, Mixpanel (just for reconciliation)

## Process

### Step 1 — Audit event data

Check:

- % of conversions with ≥ 1 known touch (if < 70%, attribution will be noisy)
- Most common `(utm_source, utm_medium)` combos — normalize before modeling
- Bot / self-referral contamination — strip
- Identity graph — do we resolve visitor → user on signup?

Produce a short **instrumentation gap report** with fixes.

### Step 2 — Build the touch journeys

For each converter, produce the ordered list of touches in the window:

```
user_abc | 2026-03-12 google/cpc → 2026-03-18 linkedin/organic → 2026-03-25 direct → SIGNUP
```

### Step 3 — Compute 5 standard models

For every conversion, compute credit under:

- **First-touch** — 100% to first channel
- **Last-touch** — 100% to last channel
- **Linear** — equal split
- **Position-based** — 40/20/40 (first, middle, last)
- **Time-decay** — exponential decay toward most recent

Report channel-level spend vs. credited revenue under each model. The spread between models is where gut feel breaks — having all 5 forces honesty.

### Step 4 — Add an "assisted" view

For each channel, report:

- Conversions where it was the ONLY touch (solo)
- Conversions where it was present but not solo (assist)
- Conversions where it was first / middle / last

This is how you spot "LinkedIn never gets last-touch credit but appears in 60% of enterprise journeys".

### Step 5 — Cross-reference with vendor attribution

Pull the same channels' reported conversions from:

- GA4
- Meta Ads Manager
- LinkedIn Ads
- Google Ads

Build the reconciliation table. Explain discrepancies. Almost always: vendor platforms over-credit themselves (view-through, click-through with long windows).

### Step 6 — Recommend a model

Based on business model, sales cycle, and data completeness, pick one model as the **source of truth**. Document the reasoning. This is the model the team uses in dashboards and weekly reports.

Also keep a secondary model for cross-checks.

### Step 7 — Instrument going forward

Produce a UTM convention spec:

- Required fields
- Source / medium / campaign naming conventions
- Rules for paid vs. organic
- Tooling implementation (e.g., campaign URL builder)

## Output artifacts

- `attribution-model.md` — methodology + chosen model + rationale
- `channel-performance.html` — interactive dashboard with all 5 models
- `utm-convention.md` — going-forward spec

## Handoff

- Chosen model → Performance Reporter (one source of truth)
- Dashboard → Growth Dashboard Builder
- UTM convention → Paid Ads Generator + Content Ideator (they tag their links consistently)
- Instrumentation gaps → eng backlog

## Example call

> "Build us an attribution model. I have events.csv with 6 months of touches and conversions.csv with our signups and paid conversions. GA4 says Google Ads drove 70% of signups; Meta Ads Manager also claims 60%. Something's double-counting."
