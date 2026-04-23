---
name: checkout-funnel-auditor
description: Audit the checkout/upgrade funnel for friction, trust, and clarity issues; produce a prioritized fix list. Use when the user says "checkout funnel audit", "why are people dropping at payment", "reduce checkout friction", or is adding a new payment path.
status: new
---

# Checkout Funnel Auditor (Revenue Squad)

Finds where payers drop off in the pricing → upgrade → confirmation flow.

## Triggers

- "audit our checkout funnel"
- "why do people drop at payment"
- "reduce checkout friction"
- "add a new payment flow — what's best practice"

## Inputs required

1. **Flow screenshots / screen recording** — pricing → plan select → payment → confirm
2. **Funnel numbers** — conversion at each step
3. **Payment methods** — card, PayPal, invoice, Apple/Google Pay, crypto
4. **Plan structure** — from Pricing Page Optimizer if available
5. **Region mix** — US vs. EU vs. RoW (affects tax + trust signals)

## Process

### Step 1 — Map the current flow

List every step the user takes. For each:

- Page / screen
- Required fields
- Trust signals visible (lock icon, VISA/MC, guarantee)
- Exit options (close, back, skip)
- Mobile behavior

### Step 2 — Run the friction checklist

Flag any of:

- Account creation required **before** payment (huge killer)
- Requiring company name / VAT when consumer
- Card form without inline validation
- No saved-card option for existing users
- Taxes / fees that only show at final step (bait-and-switch feel)
- Required email confirmation before access (delayed gratification)
- CVV / billing address order confusing
- No "apply coupon" input visible
- Mobile form with mismatched keyboard (numeric vs. text)

### Step 3 — Trust audit

- Guarantee visible on payment page (money-back, cancel anytime)
- Security signals — badge, "powered by Stripe", SSL lock
- Testimonial or quote on payment page
- Total price broken down (subtotal, tax, discount) before final CTA
- Clear renewal date / billing cadence

### Step 4 — Clarity audit

- Button text: "Pay $X/mo" > "Subscribe" > "Continue"
- Receipt-like total right above the button
- Post-purchase: confirmation + "what happens next" (not a dead-end "success" screen)

### Step 5 — Mobile-specific checks

- Single-column layout
- Apple Pay / Google Pay button above manual card form
- No hidden fields that require scroll on 375px
- Keyboard type matches input (numeric keypad for card)

### Step 6 — Write the fix list

Score each issue: **effort** (dev days) × **expected lift**. Rank by ROI. Split into:

- **Ship today** (copy, button text, trust badges)
- **This sprint** (payment rearrangement, Apple Pay add)
- **Strategic** (remove account-before-payment, new provider)

### Step 7 — Test plan

Top fix → hand to A/B Test Designer with hypothesis + sample size.

## Output artifact

`checkout-audit.md` with:

- Funnel diagram with current drop-off %
- Friction checklist with pass/fail
- Trust + clarity + mobile scores
- Prioritized fix list
- First A/B test proposal

## Handoff

- Fixes → eng
- First test → A/B Test Designer
- Any pricing-page upstream issues → Pricing Page Optimizer

## Example call

> "Audit our upgrade flow. Trial users go: dashboard → upgrade modal → plan select → Stripe checkout → success. We're losing 60% between modal and Stripe. Screenshots attached."
