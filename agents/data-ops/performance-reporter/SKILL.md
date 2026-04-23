---
name: performance-reporter
description: Build a weekly or monthly growth performance report with KPIs, trends, wins, misses, and prioritized next bets. Use when the user says "weekly growth report", "monthly growth update", "board-ready report", or is wrapping up a campaign.
status: wrapper
upstream: marketing:performance-report
---

# Performance Reporter (Data Ops)

Wrapper for `marketing:performance-report`. Standardized to a "5 things" stakeholder format.

## Triggers

- "weekly growth report"
- "monthly marketing update"
- "board-ready growth snapshot"
- "end-of-campaign report"

## Inputs

- Current dashboard (Revenue + Growth)
- Campaigns shipped in the period
- Experiments concluded
- Qualitative notes (customer calls, team learnings)

## Process

1. **Invoke upstream** to produce the base report.
2. **Force the "5 things" structure:**
   1. **North-star movement** — number, direction, context
   2. **Biggest win** — what happened, why it worked
   3. **Biggest miss** — what happened, what we learned
   4. **What changed** — shipped this period
   5. **Next bets** — 3 prioritized bets with owners + hypotheses
3. **Rule**: Never report a metric without a next action or a learning.

## Output artifact

`growth-report-YYYYMMDD.md` (and `.docx` via `anthropic-skills:docx` for stakeholder distribution).

## Handoff

Report feeds into leadership comms. "Next bets" → becomes next period's A/B Test Designer queue.
