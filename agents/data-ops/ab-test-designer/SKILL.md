---
name: ab-test-designer
description: Design an A/B test with hypothesis, sample size, primary + guardrail metrics, analysis plan, and stop rules. Use when the user says "design an A/B test", "test <change>", "run an experiment on X", or is about to ship a change without a test plan.
status: new
---

# A/B Test Designer (Data Ops)

Turns a proposed change into a rigorous test spec. Every field is required — no "we'll figure it out later".

## Triggers

- "design an A/B test for X"
- "test this landing page change"
- "experiment plan for <feature>"
- "how should we test <change>"
- "what's the sample size for <test>"

## Inputs required

1. **Change being tested** — control + variant(s) described precisely
2. **Where** — page, flow, user segment
3. **Why** — the belief driving the test (will be converted to a hypothesis)
4. **Primary metric** — what you hope will move
5. **Current conversion rate + weekly volume** — to compute sample size

## Process

### Step 1 — Convert the belief into a hypothesis

Force the `If X, then Y, because Z` shape:

> If we <change>, then <metric> will <direction>, because <user behavior reason>.

If the user can't articulate the `because`, the test isn't ready — push back.

### Step 2 — Define metrics

- **Primary** — the outcome the hypothesis moves (trial signup, activation, upgrade)
- **Secondary** — downstream effects you also care about
- **Guardrails** — metrics that should NOT regress (bounce rate, NPS, support volume, revenue per visit)

Rule: every test needs **at least one guardrail**. No exceptions.

### Step 3 — Power calculation

Compute sample size using:

- Baseline conversion rate
- Minimum detectable effect (MDE) — the smallest lift worth acting on
- Statistical power (default 80%)
- Significance threshold (default 95%)

Return:

- Sample per variant
- Total weeks of data needed
- What to do if baseline traffic is too low (options: raise MDE, extend duration, pool segments, kill the test)

Flag underpowered tests honestly. Many growth teams ship tests that can never reach significance — don't let them.

### Step 4 — Design the test

- **Variants** — control + 1 (A/B) or control + 2 (A/B/n). Avoid > 2 variants unless you have 3× the traffic.
- **Randomization unit** — user (sticky), session, or visit — pick intentionally
- **Exclusions** — internal users, bot traffic, specific segments if contaminating
- **Holdout** — 5–10% holdout if this is a permanent ship if it wins

### Step 5 — Pre-register the analysis plan

Before the test runs, write down:

- The exact SQL / query that will compute each metric
- How you'll handle outliers
- How you'll segment results (by plan, source, device, etc.)
- What result would cause you to roll back even if primary metric wins

### Step 6 — Stop rule

- **Planned stop:** after target sample size reached
- **Early stop:** only if a guardrail crosses a pre-declared threshold
- **Do not stop early on winning** — this inflates false-positive rate

### Step 7 — Output the test doc

Produce a single-page test spec with all of the above.

## Output artifact

`test-<change-name>.md` with:

- Hypothesis
- Variants + screenshots
- Metrics (primary, secondary, guardrails)
- Sample size + duration
- Randomization + exclusions
- Analysis plan
- Stop rule
- Owner + launch date + review date

## Handoff

- Eng ships the test
- Data Ops runs the analysis on review date
- Performance Reporter surfaces the result in the next report
- Null results are logged as a **learning** — not hidden

## Example call

> "Design an A/B test for moving our pricing page CTA from 'Start free trial' to 'Try it free — no card'. Current page CVR is 4%. ~5,000 visitors/week. MDE I care about is +15% relative."
