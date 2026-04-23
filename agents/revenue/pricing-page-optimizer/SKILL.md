---
name: pricing-page-optimizer
description: Audit a pricing page for plan structure, anchoring, feature matrix, and CTA clarity; produce a rewritten version with rationale. Use when the user says "audit our pricing page", "rewrite pricing", "are we priced right", or is repricing/repackaging.
status: new
---

# Pricing Page Optimizer (Revenue Squad)

Audits pricing with a pricing-psychology + conversion lens, then rewrites the page.

## Triggers

- "audit our pricing page"
- "rewrite pricing"
- "are we priced right"
- "help with repackaging"
- "why do people bounce from pricing"

## Inputs required

1. **Pricing page URL** or screenshot
2. **Current plan / price structure** — names, prices, what's included
3. **Competitor pricing** — 2–5 competitors' public pricing pages
4. **Customer mix** — % on each plan, avg ARPU
5. **Who lands here** — segment + funnel stage
6. **Conversion rate** — pricing page → trial / purchase

## Process

### Step 1 — Audit plan structure

Check for:

- **Plan count** — 3 is the sweet spot; 4 only if you have a distinct enterprise tier
- **Decoy effect** — is the middle plan clearly the best value?
- **Anchoring** — is the highest plan visible enough to anchor high?
- **Usage-based vs. seat-based** — does the structure match how customers actually grow?
- **Annual discount** — is it compelling (≥ 15%)? Is the default toggle annual or monthly?

### Step 2 — Audit naming

Plans named by:

- **Persona** (Solo / Team / Business) — usually best for self-serve
- **Scale** (Starter / Pro / Enterprise) — classic
- **Use case** (Build / Ship / Scale) — aspirational

Avoid cute names that require explanation. "Hobbyist / Pro / Enterprise" beats "Acorn / Oak / Forest" every time.

### Step 3 — Audit the feature matrix

- Matrix must be scannable in 10 seconds
- Most important differentiator at the top
- Checkmark-only rows with no numbers make plans feel identical — add quantified differences (5 projects vs. unlimited)
- Unlimited should be at the top tier only

### Step 4 — Audit hero + CTA

- Hero answers "who is each plan for" in one line per plan
- Each plan has ONE CTA — not "Start trial" AND "Contact sales"
- Free tier / trial CTA is dominant
- No pricing below the fold

### Step 5 — Audit objection handling

- FAQ below the table covering: refunds, annual switching, team billing, security/compliance, trial terms
- Social proof section (logos + 1 quote per plan tier where possible)
- Money-back / trial guarantee

### Step 6 — Rewrite

Produce a rewritten pricing page with:

- Rewritten hero line per plan
- Cleaned feature matrix (flag rows to cut, rows to add)
- Rewritten CTAs
- Suggested FAQ items
- Before → after for each change with rationale

### Step 7 — Test plan

Recommend 1–2 A/B tests (plan name swap, annual-default toggle, CTA copy). Hand to A/B Test Designer.

## Output artifact

`pricing-audit.md` with score card + rewrites + test plan.

## Handoff

- Rewrites → eng / design
- Test plan → A/B Test Designer
- Plan-mix shift implications → Revenue Dashboard Builder

## Example call

> "Audit acme.com/pricing. We have Free / Pro ($20) / Business ($80) / Enterprise (call us). 80% of paid users are on Pro. Competitors: linear.app, asana.com. Page CVR is 4% pricing → trial."
