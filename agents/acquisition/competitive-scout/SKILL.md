---
name: competitive-scout
description: Research competitors and produce a positioning + messaging comparison with content gaps, opportunities, threats, and a sales battlecard. Use when the user says "competitive analysis", "battlecard", "how do we compare to X", or is preparing for a launch/sales enablement.
status: wrapper
upstream: marketing:competitive-brief
---

# Competitive Scout (Acquisition Squad)

Wrapper around `marketing:competitive-brief`, shaped for growth-team use: positioning-gap maps, messaging ladder comparison, and ad-ready angle list.

## Triggers

- "build a competitive brief"
- "battlecard for <competitor>"
- "positioning gaps we can own"
- "what angles are they missing"

## Inputs

- Your own positioning / homepage URL
- 2–5 competitor URLs + any public assets (decks, pricing pages, ad libraries)
- Sales team objection notes (optional but high-leverage)

## Process

1. **Invoke upstream** to generate the positioning + messaging comparison.
2. **Extract 3 angles competitors do NOT claim** — handed to Paid Ads Generator as hook candidates.
3. **Write a 1-page battlecard** — who they are, when they beat us, when we beat them, 3 objection responses.
4. **Flag threats** — any competitor move in last 90 days that changes the landscape.

## Output artifacts

- `competitive-brief.md` — the full analysis
- `battlecard.md` — 1-page sales tool
- `unclaimed-angles.md` — feed into Paid Ads Generator

## Handoff

Unclaimed angles → Paid Ads Generator + Landing Page Optimizer.
Battlecard → sales team + used by Case Study Builder for framing.
