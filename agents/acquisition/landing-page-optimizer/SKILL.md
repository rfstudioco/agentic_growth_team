---
name: landing-page-optimizer
description: Audit a landing page for message-match, hierarchy, scannability, and conversion design; produce a rewritten version with annotated fixes. Use when the user says "review our landing page", "optimize this page for conversion", "rewrite our homepage hero", or is about to run paid traffic to a page.
status: new
---

# Landing Page Optimizer (Acquisition Squad)

Audits a landing page section-by-section against an explicit conversion checklist, then rewrites the weakest sections.

## Triggers

- "optimize landing page <url>"
- "audit our homepage for conversion"
- "rewrite the hero"
- "why isn't this page converting"
- "landing-page review before we send paid traffic"

## Inputs required

1. **Page URL** or screenshot / HTML
2. **Traffic source** — where visitors come from (organic, paid, email, direct)
3. **Matching ad/post copy** — what they saw right before the page
4. **ICP** — from ICP Researcher
5. **Primary conversion** — what single action should this page drive
6. **Current conversion rate** (if known)

## Process

### Step 1 — Pull the page and break into sections

Sections to identify:

```
Hero · Social proof · Problem · Solution · How it works ·
Benefits · Features · Objections · Pricing · CTA · Footer
```

Flag missing critical sections.

### Step 2 — Run the audit checklist

For each section, score on:

- **Message match** — does it mirror the source ad/search intent? (Y/N)
- **Hierarchy** — can a 5-second skim answer "what is this and is it for me?" (Y/N)
- **Specificity** — concrete claims > vague adjectives (1–5)
- **Proof** — is there evidence for every major claim? (Y/N)
- **Friction** — any form field or choice that isn't essential? (count)
- **Mobile legibility** — does hero render correctly on 375px wide? (Y/N)

### Step 3 — Apply diagnostic heuristics

Common failure modes to check:

- **Hero fails the 5-second test** — can't tell what the product is
- **"We/our" opening instead of "you"** — self-referential
- **Features before benefits** — what before why
- **Hidden value prop** — requires scroll to see what you do
- **Social proof as logo wall only** — no quotes, numbers, or names
- **Single CTA missing above the fold** — or worse, competing CTAs
- **No objection handling** — FAQ below the fold is critical

### Step 4 — Rewrite the weakest sections

Rewrite sections scoring ≤ 3/5, following this priority:

1. Hero
2. Primary CTA + button copy
3. Problem statement (or add one if missing)
4. First proof section

Provide the rewrite + a plain-English rationale for each change.

### Step 5 — Output the audit

Produce:

- **Scorecard** — section × criterion table
- **Top 5 fixes** — ranked by expected impact
- **Rewrites** — section-by-section with before → after
- **Test plan** — which fix to A/B test first (hand to A/B Test Designer)

## Output artifact

`landing-page-audit-<domain>.md`.

## Handoff

- Rewrites → eng / Webflow for implementation
- Test plan → A/B Test Designer
- Message-match issues → back to Paid Ads Generator to align source ads

## Example call

> "Audit and optimize acme.com/pricing. Paid traffic source is Meta. ICP is SMB e-commerce founders. Primary conversion is 'Start free trial'. Current CVR is 1.3%."
