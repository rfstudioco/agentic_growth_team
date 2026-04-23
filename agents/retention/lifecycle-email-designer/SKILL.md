---
name: lifecycle-email-designer
description: Design ongoing lifecycle drip + milestone emails for users past the welcome phase. Use when the user says "lifecycle emails", "retention drip", "milestone email series", or is planning month-2+ communications.
status: wrapper
upstream: marketing:email-sequence
---

# Lifecycle Email Designer (Retention Squad)

Wrapper for `marketing:email-sequence` scoped to weeks 3+ of the user lifecycle.

## Triggers

- "lifecycle emails"
- "post-onboarding drip"
- "milestone email series"
- "engagement emails"

## Inputs

- Activation definition + current D30 retention curve
- Key lifecycle milestones (first X done, feature Y adopted, Nth login)
- Segment splits by plan / usage band

## Process

1. **Invoke upstream** to produce the base sequence.
2. **Shape for retention:**
   - Every email tied to a milestone or behavior, not a calendar date
   - Include "we noticed you haven't tried X" branch
   - Include "you just hit milestone Y — here's what usually comes next" branch
   - Expansion hooks tagged for Upsell Sequencer
3. **Declare metric hypothesis** — e.g., "this sequence should lift W12 retention by 3pp".

## Output artifact

`lifecycle-emails.md` with flow diagram, per-email spec, and handoff rules.

## Handoff

Expansion-ready signals → Upsell Sequencer.
Dormant-detection → Re-engagement Campaigner.
