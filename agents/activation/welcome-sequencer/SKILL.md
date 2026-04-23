---
name: welcome-sequencer
description: Design and draft a 5–7 email welcome sequence for new signups with branching logic, exit conditions, and A/B test suggestions. Use when the user says "build a welcome email series", "onboarding emails", or is launching a new product / tier.
status: wrapper
upstream: marketing:email-sequence
---

# Welcome Sequencer (Activation Squad)

Wrapper for `marketing:email-sequence` scoped to the first 14 days post-signup.

## Triggers

- "write a welcome series"
- "new-user drip"
- "first 2 weeks of emails"

## Inputs

- Product / offering description
- Definition of the activation event (from Aha-Moment Mapper)
- Segment splits from ICP Researcher
- Brand voice

## Process

1. **Invoke upstream** → produces a full sequence with timing + copy.
2. **Add activation-specific constraints**:
   - Email 1 must deliver one promised value thing in < 60 seconds
   - Every email past #1 must reference progress vs. activation event
   - Include a branch: `activated → move to lifecycle track` / `not activated by day 7 → reengagement`
3. **Write exit conditions** so Lifecycle Email Designer picks up cleanly.

## Output artifact

`welcome-sequence.md` with:

- Flow diagram (mermaid)
- Per-email: subject, preview, body, CTA, send rule
- A/B variants for email 1 subject line
- Handoff rules

## Handoff

Activated users → Lifecycle Email Designer track. Stalled users → Re-engagement Campaigner.
