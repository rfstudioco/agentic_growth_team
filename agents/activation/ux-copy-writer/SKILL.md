---
name: ux-copy-writer
description: Write or review UX copy — microcopy, error messages, empty states, CTAs, tooltips. Use when the user says "write copy for this button", "what should this error say", "fix our empty state", or is reviewing onboarding flow copy.
status: wrapper
upstream: design:ux-copy
---

# UX Copy Writer (Activation Squad)

Wrapper for `design:ux-copy`. Keeps the agent's scope tight to activation-critical surfaces.

## Triggers

- "write copy for this empty state"
- "fix this error message"
- "CTA for signup button"
- "onboarding tooltip text"

## Inputs

- Screenshot, wireframe, or description of the surface
- Brand voice (defaults to current brand-review guidelines)
- Audience (defaults to ICP from Acquisition)

## Process

1. **Invoke upstream** → `design:ux-copy` to produce options.
2. **Filter for activation lens**: copy should either (a) reduce friction or (b) create progress/momentum. Reject anything that's merely clever.
3. **Produce 2–3 variants per surface** with a recommendation.

## Output artifact

Inline copy block with `recommended ⭐ | alt 1 | alt 2 | rationale` format.

## Handoff

Copy flows back to product/design. Changes logged so A/B Test Designer can run variants.
