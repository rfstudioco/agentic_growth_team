---
name: feature-adoption-tracker
description: Monitor adoption of key features across your user base, identify non-adopters of sticky features, and generate targeted in-product + email nudges. Use when the user says "track feature adoption", "nudge users to try X", "which features drive retention", or is rolling out a new feature.
status: new
---

# Feature Adoption Tracker (Retention Squad)

Continuous loop: measure which features predict retention, find users not using them, nudge, measure lift.

## Triggers

- "track feature adoption"
- "why isn't anyone using <feature>"
- "nudge users who haven't tried X"
- "which features drive retention"
- "rolling out <feature> — how do we drive adoption"

## Inputs required

1. **Feature inventory** — list of trackable features with the event name for each
2. **Event data** — 60+ days of feature-use events
3. **Retention cohorts** — from Cohort & Churn Analyzer
4. **User attributes** — plan, tenure, activation status

## Process

### Step 1 — Rank features by retention impact

For each feature:

- % of active users who have used it at least once
- Retention lift of users who used it vs. users who haven't (matched on tenure + plan)
- Confidence interval on that lift

Split features into four quadrants:

```
                   High adoption       Low adoption
High lift     ✅ Sticky core        🟡 Hidden gem
Low lift      ⚪️ Table stakes      🔴 Feature bloat
```

Focus attention on **Hidden gems** — high lift, low adoption.

### Step 2 — Identify non-adopter segments

For each Hidden Gem feature, build a segment:

- Active (used product in last 14 days)
- Has NOT used feature in last 30 days
- Matches the profile of users who normally use it (plan / tenure)

This is the nudge queue.

### Step 3 — Design the nudge

For each feature, write:

- **In-app banner** — shown once, dismissible
- **Empty-state nudge** — if there's a relevant empty state in the product
- **Email** — sent only if in-app didn't trigger adoption within 7 days

Copy rules:

- Lead with outcome, not feature name
- Include a 1-click path to try it
- Show proof ("teams who use this get to W4 14% more often")

### Step 4 — Instrument the loop

- `<feature>_nudge_shown`
- `<feature>_nudge_clicked`
- `<feature>_first_use`

Measure conversion from nudge → first use → second use (adoption sticks) → retention lift vs. a held-out control.

### Step 5 — Output

Produce:

- **Feature heatmap** — quadrant view of adoption vs. retention impact
- **Nudge queue** — per-feature, per-user list (CSV)
- **Copy spec** — in-app + email for each feature
- **Measurement plan**

## Output artifacts

- `feature-adoption-heatmap.html`
- `nudge-queue.csv`
- `nudge-copy.md`

## Handoff

- Nudges → product (in-app) + Lifecycle Email Designer (email)
- Adoption lift results → Performance Reporter
- Features in the "bloat" quadrant → consider deprecating (feed to product PM)

## Example call

> "Analyze our feature usage in events.csv. Find which features are 'hidden gems' — low adoption but strongly predict retention — then give me a nudge queue for Pro-plan users who haven't used our integrations feature."
