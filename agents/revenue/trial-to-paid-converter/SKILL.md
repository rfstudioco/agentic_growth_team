---
name: trial-to-paid-converter
description: Design a trial-to-paid conversion playbook with usage-personalized nudges (in-app + email) timed to the trial countdown. Use when the user says "increase trial conversion", "trial-to-paid flow", "convert more free users", or is launching a new trial.
status: new
---

# Trial-to-Paid Converter (Revenue Squad)

Builds the in-trial experience. Every nudge is personalized to what the user has (or hasn't) done so far.

## Triggers

- "increase trial conversion"
- "trial-to-paid flow"
- "convert more free users"
- "what should we email trialists"
- "redesign the trial"

## Inputs required

1. **Trial length** — 7, 14, 30 days
2. **Trial type** — opt-in credit card, reverse trial, freemium with time-limited features
3. **Activation event** — from Aha-Moment Mapper
4. **Current trial-to-paid rate** (if known)
5. **Feature access** — what's locked in trial vs. paid
6. **Event data** — so we can personalize by actual usage

## Process

### Step 1 — Pick a trial archetype

- **Opt-in (card required)** — highest CVR, lowest signup
- **Reverse trial** — full product for 14 days then downgrade to free
- **Freemium with time-locked features** — lowest friction, hardest to convert

Recommend one based on ICP + AOV. Note tradeoffs.

### Step 2 — Segment trialists by usage signal

At each check-in point (day 1, 3, 7, trial-end):

| Segment | Signal | Right message |
|---|---|---|
| **Activated** | Hit aha event | "Here's what advanced users do next" |
| **Trying** | Some activity but not aha | "You're close — try this one thing" |
| **Ghosts** | Signed up, did nothing | Reactivation hook or archive |
| **Power** | 3x normal usage | Upgrade nudge early + account manager reach-out if value tier |

### Step 3 — Design the in-trial flow

Per segment, per day, specify:

- **In-app:** banner, progress bar, tooltip, or modal
- **Email:** subject + body + CTA
- **Sales touch:** only for power users above ARR threshold

Critical beats:

- **Day 0:** Welcome + checklist to aha
- **Day of activation:** "Congrats — here's what's possible"
- **Day before trial end:** Show value delivered + upgrade CTA with total
- **Trial end day:** Upgrade prompt + easy path to extension (maybe 7 days) if they ask
- **Day after trial end:** One last email with value recap + compelling offer

### Step 4 — Price anchoring during trial

- Show plan they're on if upgraded
- Show total saved with annual
- Show features they're using that they'll lose if they don't upgrade
- Avoid loss-aversion hammering — once, not five times

### Step 5 — Declare hypothesis + metric targets

- Primary: trial-to-paid rate
- Guardrails: trial-end unsubscribe rate, post-trial NPS

Hand to A/B Test Designer for structured test.

## Output artifact

`trial-conversion-playbook.md` with:

- Archetype recommendation
- Per-segment × per-day matrix
- Copy for every message (in-app + email)
- Sales touch rules
- Metrics spec

## Handoff

- In-app → product / design
- Emails → Lifecycle Email Designer runbook
- Sales touches → sales ops
- Trial-end upsells → Upsell Sequencer

## Example call

> "We have a 14-day trial with card required. Trial-to-paid is 18%. ICP is RevOps at 50–500 person SaaS. Activation is 'connect a data source AND build a first report'. Help me redesign the trial experience."
