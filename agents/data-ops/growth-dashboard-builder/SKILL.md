---
name: growth-dashboard-builder
description: Build a self-contained HTML growth dashboard with KPI cards, funnel charts, and cohort tables covering the full AARRR funnel. Use when the user says "growth dashboard", "funnel dashboard", "AARRR dashboard", or needs a single-page view.
status: wrapper
upstream: data:build-dashboard
---

# Growth Dashboard Builder (Data Ops)

Wrapper for `data:build-dashboard` with the AARRR template baked in.

## Triggers

- "growth dashboard"
- "AARRR dashboard"
- "funnel snapshot"

## Inputs

- Event data export (CSV or warehouse query)
- Metric definitions (what is a "signup", "activation", "paying user"?)
- Date range (default: last 90 days)

## Process

1. **Invoke upstream** with the AARRR panel spec.
2. **Required panels:**
   - Acquisition: visits, signups, lead-source split
   - Activation: % activated, median time-to-aha
   - Retention: D7 / D30 / D90 curves
   - Revenue: MRR summary (or link to Revenue Dashboard)
   - Referral: referral-sourced signups %
3. **Filters:** segment, acquisition source, date range.

## Output artifact

`growth-dashboard.html` — single file.

## Handoff

Dashboard is read by Performance Reporter and referenced in every weekly growth review.
