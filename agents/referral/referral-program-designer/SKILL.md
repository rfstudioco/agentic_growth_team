---
name: referral-program-designer
description: Design a referral program from scratch — mechanics, double-sided incentives, incentive math, tracking spec, launch plan. Use when the user says "design a referral program", "launch a referral", "referral incentives", "viral loop", or is planning the advocacy lever.
status: new
---

# Referral Program Designer (Referral Squad)

Produces the mechanics, math, and launch plan for a referral program — not vague "share for a discount" ideas.

## Triggers

- "design a referral program"
- "launch a referral"
- "what incentive should we offer"
- "viral loop design"
- "refer-a-friend program"

## Inputs required

1. **Pricing** — ARPU, gross margin
2. **CAC** — paid and blended
3. **Current referral rate** — % of new customers who say "referred by friend"
4. **Payment model** — subscription, one-time, usage-based
5. **ICP** — are these people who would share (prosumer/team tools yes; enterprise often no)
6. **Brand tolerance** — can you do "get $20 when your friend signs up" or is that too cheap?

## Process

### Step 1 — Decide the program type

- **Double-sided discount** — both get X (e.g., Dropbox, Airbnb)
- **Giver-only reward** — referrer gets credit, referee gets nothing special
- **Receiver-only discount** — referee gets a discount, referrer gets nothing (weakest)
- **Cash payout** — straight cash per qualified signup (best for high-ticket)
- **Gift** — physical item per referral (expensive, high emotional impact)

Recommend one based on inputs, with tradeoffs explicit.

### Step 2 — Do the incentive math

Constraint: incentive per customer < 30% of CAC_paid. If you beat paid CAC, you win.

Work out:

- Cost per referred customer = incentive (giver) + incentive (receiver) + platform/tooling amortized
- Expected LTV of referred customers (often 1.2–1.5× organic average — calculate from data if possible)
- Payback period
- Break-even referral rate

Output a simple model: "at X referral rate and Y payout, we add $Z MRR/month at W payback months."

### Step 3 — Define qualification

What counts as a successful referral?

- **Signed up** — weak, easy to game
- **Activated** — recommended default (tied to Aha-Moment Mapper)
- **Paid** — strongest, most aligned with revenue
- **Paid 30 days** — kills fraud, for high-ticket items

### Step 4 — Design the mechanics

- How do users get a referral link? (in-app, profile page, email)
- How is attribution tracked? (unique URL, promo code, hybrid)
- When does the incentive pay out? (on qualification)
- How do users see progress? (leaderboard? just a total?)
- Fraud controls — limit per user, block same-IP signups, block self-referrals

### Step 5 — Write the launch plan

- Pre-launch: invite 50 top NPS users (from Advocate Identifier) to try it first
- Launch: in-app modal for all users, email blast to existing customer base
- Amplification: case study of early referral wins; social proof in pricing page
- Post-launch: weekly referral leaderboard email to participants

### Step 6 — Instrumentation + metrics

Events:

- `referral_link_created`
- `referral_link_clicked`
- `referred_signup`
- `referred_activated`
- `referral_payout_issued`

Metrics:

- Primary: % of new customers via referral
- Secondary: referrals per referrer, activation rate of referred vs. organic, CAC_referral

### Step 7 — Write the ToS / rules

- Who can refer
- Caps
- Payout timing
- Refunds / clawback if referred churns in 30 days

## Output artifact

`referral-program.md` with:

- Program type + rationale
- Incentive math model
- Mechanics + fraud controls
- Launch plan
- Events + metrics spec
- ToS skeleton

## Handoff

- Mechanics → eng / tooling (Rewardful, Partnero, custom)
- Launch email → Lifecycle Email Designer
- Invite list → Advocate Identifier
- Performance → Performance Reporter

## Example call

> "Design a referral program. ARPU $29/mo, gross margin 85%, blended CAC $110. Current referral rate ~5%. SaaS, self-serve, prosumer. We can offer up to $15 per successful referral."
