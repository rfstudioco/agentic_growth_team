---
name: case-study-builder
description: Run an end-to-end case study pipeline — interview questions → story extraction → publish-ready case study with metrics and quotes. Use when the user says "write a case study", "turn this customer into a case study", "interview customer X for a story", or is building proof assets.
status: new
---

# Case Study Builder (Referral Squad)

Converts a happy customer into a published case study without the usual fluff. Opinionated format.

## Triggers

- "write a case study"
- "turn customer X into a case study"
- "interview our customer for a story"
- "proof asset for <ICP>"

## Inputs required

1. **Customer name + contact**
2. **What they bought / how they use the product**
3. **Rough outcome** — any metrics they've shared (even anecdotal)
4. **Interview transcript** OR permission to generate interview questions first
5. **Target audience** — which ICP segment is this case study for

## Process

### Step 1 — Pre-interview: generate the interview guide

If no transcript yet, produce a 30-minute interview guide following this spine:

1. **Before** — what was life like before our product? (pain)
2. **Trigger** — what made you start looking? (event)
3. **Evaluation** — what did you consider? (alternatives)
4. **Adoption** — how did you roll it out? (process)
5. **Outcome** — what changed? (result — push for numbers)
6. **Future** — what's next? (aspiration)

Include **specific follow-up prompts** under each:

- "Can you quantify that?"
- "What would have happened if you hadn't solved this?"
- "What's a concrete moment that sticks out?"

### Step 2 — Post-interview: extract the story

From the transcript, pull:

- **3 numbers** — real metrics with context (e.g., "cut onboarding from 2 weeks to 3 days")
- **3 quotes** — verbatim, emotional, specific (no "it's been a game-changer")
- **1 scene** — a concrete moment that anchors the whole story
- **1 risk** — what they were afraid of that didn't happen

If you can't find all of these, the case study isn't ready — flag it and suggest a second interview.

### Step 3 — Draft the case study

Use this opinionated structure:

```
Headline          — outcome-focused, specific number if possible
Subhead           — who they are, one line
The problem       — 2 paragraphs, pain + trigger
The alternative   — what they tried before or considered
The solution      — how they use the product (specific workflow)
The results       — 3 numbers, in a row, with context
Quote             — their strongest pull quote, big and pulled out
What's next       — 1 paragraph, forward-looking
CTA               — "book a demo / start free / talk to sales"
```

Rules:

- Lead with outcome, not "meet <customer>"
- Avoid corporate-speak ("leverage", "synergy", "empower")
- One quote per section max
- Always link to ICP — "if you're a <ICP>, this is you"

### Step 4 — Approval loop

Produce a draft + a bulleted list of:

- Facts to confirm
- Quotes to approve verbatim
- Numbers that need written permission

Send to customer for review before publishing.

### Step 5 — Package for distribution

Produce three versions:

- **Long** — web page (markdown / HTML)
- **Short** — 500 words for email + PDF
- **Snippets** — 3 pull quotes + 3 numbers formatted for paid ads (hand to Paid Ads Generator)

## Output artifacts

- `case-study-<customer>.md` (long)
- `case-study-<customer>-short.md` (email / PDF)
- `case-study-<customer>-snippets.md` (ads, landing page, social)

## Handoff

- Snippets → Paid Ads Generator + Landing Page Optimizer
- Customer outreach → Advocate Identifier (are they open to reference calls?)
- Published → Performance Reporter (track the asset's impact)

## Example call

> "Write a case study on Acme Co. They moved from Salesforce to us 6 months ago. Champion is Jane, VP Sales. I have a 45-min call transcript attached. Target audience: mid-market RevOps leaders."
