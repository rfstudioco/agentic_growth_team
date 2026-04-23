---
name: icp-researcher
description: Build a falsifiable Ideal Customer Profile from interviews, data, and competitor signals. Use when the user says "build an ICP", "who should we sell to", "refine our ICP", "define our customer segment", or is kicking off any growth motion without a clear ICP.
status: wrapper
upstream: design:user-research
---

# ICP Researcher (Acquisition Squad)

Wrapper agent. Delegates the research method to `design:user-research` and shapes the output for growth use.

## Triggers

- "build an ICP"
- "refine our ideal customer profile"
- "who should we sell to"
- "who's actually getting value"
- any growth planning request where segment is undefined

## Inputs

- Existing customer list (any form: CRM export, spreadsheet, anecdotes)
- 3–8 customer interview transcripts or recordings
- Competitor target-user pages (URLs or screenshots)
- Win/loss notes if available

## Process

1. **Delegate discovery** → invoke `design:user-research` with the inputs to cluster users by pain, context, and job-to-be-done.
2. **Add growth layering** that the upstream skill doesn't produce:
   - **Firmographics** — company size, industry, stage, geography
   - **Trigger event** — what happens right before they start looking for a solution
   - **Channel** — where this segment already hangs out
   - **Anti-ICP** — explicit list of who we should NOT pursue
3. **Write a falsifiable hypothesis** — "We believe _[segment]_ buys because _[trigger]_; this is wrong if _[observable]_."
4. **Output the ICP one-pager** (see below).

## Output artifact

A single markdown file `icp.md` with:

```
# ICP: <segment name>

## Who they are (firmographics + role)
## What they're trying to do (JTBD)
## What triggers the search
## Where they hang out (channels)
## Why we win / lose
## Falsifiable hypothesis
## Anti-ICP (who we DON'T serve)
```

## Handoff

Passes `segment` tag into Content Ideator, Paid Ads Generator, and the Welcome Sequencer.

## Example call

> "Build an ICP for us based on these 6 customer call transcripts and the 40-row CRM export."
