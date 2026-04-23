---
name: nps-synthesizer
description: Synthesize NPS responses and open-ended survey feedback into themes, segments, and prioritized actions. Use when the user says "analyze our NPS", "summarize this survey", "what do users actually want", or has qualitative text to distill.
status: wrapper
upstream: design:research-synthesis
---

# NPS Synthesizer (Retention Squad)

Wrapper for `design:research-synthesis`. Adds growth-specific scoring + advocate flagging.

## Triggers

- "analyze our NPS"
- "synthesize survey responses"
- "what are users saying"
- "churn interview themes"

## Inputs

- NPS export (CSV of score + comment + user metadata)
- OR raw survey / interview text
- User metadata (plan, tenure, usage) if available

## Process

1. **Invoke upstream** to extract themes, patterns, and segments.
2. **Add growth-specific layering:**
   - **Promoters (9–10)** → hand to Advocate Identifier (candidate list)
   - **Passives (7–8)** → tag reasons, hand to Feature Adoption Tracker
   - **Detractors (0–6)** → cluster reasons, prioritize top 3 for fix
3. **Produce an action list** — top 5 fixes + owner + expected retention lift.

## Output artifact

`nps-synthesis.md` with themes, segment breakdowns, and action list.

## Handoff

Promoters → Advocate Identifier + Case Study Builder.
Detractor themes → product / eng backlog.
Passive reasons → Feature Adoption Tracker.
