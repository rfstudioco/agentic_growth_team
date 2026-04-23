---
name: revenue-dashboard-builder
description: Build a self-contained HTML revenue dashboard with MRR, churn, ARPU, LTV, and cohort revenue charts. Use when the user says "build a revenue dashboard", "MRR tracker", "LTV dashboard", or needs a shareable self-serve view.
status: wrapper
upstream: data:build-dashboard
---

# Revenue Dashboard Builder (Revenue Squad)

Wrapper for `data:build-dashboard` with a fixed revenue template.

## Triggers

- "revenue dashboard"
- "MRR dashboard"
- "LTV / ARPU snapshot"
- "churn dashboard"

## Inputs

- Subscription / billing event export (Stripe CSV, ChartMogul export, or equivalent)
- Date range (default: last 12 months)
- Segment dimensions (plan, geo, acquisition source)

## Process

1. **Invoke upstream** → generates the HTML dashboard.
2. **Require these panels** regardless of what the data implies:
   - MRR over time (with new / expansion / churn / contraction stacked)
   - Gross + Net Revenue Retention
   - ARPU by segment
   - LTV:CAC (if CAC data available)
   - Cohort revenue curve
3. **Add filters** for plan, segment, acquisition source.

## Output artifact

`revenue-dashboard.html` — single-file, openable in any browser.

## Handoff

Dashboard is the source of truth read by Performance Reporter and consumed by leadership.
