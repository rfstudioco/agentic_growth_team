---
name: reengagement-campaigner
description: Design a win-back campaign for dormant users with channel fallback (email → in-app → SMS → human) and exit/unsubscribe logic. Use when the user says "win-back campaign", "reengagement flow", "revive dormant users", or has a big inactive cohort.
status: new
---

# Re-engagement Campaigner (Retention Squad)

Designs a multi-touch, multi-channel win-back flow for dormant users. Optimizes for "wake them up without burning them out".

## Triggers

- "win-back campaign"
- "reengagement flow for dormant users"
- "revive churned trials"
- "we have 10k inactive users — what do we do"

## Inputs required

1. **Dormancy definition** — e.g., "no login in 30 days" (from Cohort & Churn Analyzer)
2. **Save list** (from Cohort & Churn Analyzer) — prioritized by risk or value
3. **Channels available** — email (always), in-app banner, push, SMS, human outreach
4. **Offer inventory** — discounts, content, feature unlocks, 1:1 time you can give away
5. **Budget + time horizon**

## Process

### Step 1 — Segment the dormant population

Split into tiers:

- **High-value dormant** — paying, big account, or high-LTV potential. Worth human outreach.
- **Medium-value dormant** — activated once, reachable by email + in-app.
- **Low-value dormant** — never activated. Probably never will. Consider archiving.

Design a distinct flow per tier.

### Step 2 — Pick the wake-up hook

For each tier, choose one of:

- **New thing** — "since you left, we shipped X that solves Y"
- **Progress tease** — "you were 2 steps from <aha>; we'll finish the setup for you"
- **Personal** — 1:1 offer from a human (high-value only)
- **Nostalgia / recap** — "here's what you built last time"
- **Last-chance** — "we'll delete your account in 14 days unless..."

### Step 3 — Design the sequence per tier

Template structure (7–14 day window):

| Day | Channel | Goal |
|---|---|---|
| 0 | Email | Wake-up hook |
| 3 | In-app banner (if they come back) | Show progress |
| 5 | Email | Offer / content |
| 7 | SMS or push (if opted in) | Last nudge |
| 10 | Human outreach (high-value only) | 1:1 offer |
| 14 | Email | Last-chance + respectful exit |

### Step 4 — Write the copy

For each message:

- Subject (if email) / headline (if in-app / push)
- Body — ≤ 80 words
- CTA — one action, no branching
- Unsub-friendly tone — the point is to win back, not annoy

### Step 5 — Set exit conditions

Rules:

- **Wake-up exit** — they log in → move to Welcome Sequencer's "back from dormant" track
- **Annoyance exit** — they unsubscribe or report spam → immediate stop, no more wins-back for 90 days
- **Respectful exit** — after the last message, if no response → archive. Don't stay in the sequence forever.

### Step 6 — Declare hypothesis + guardrails

- Primary: wake-up rate (user performs any action within 14 days)
- Guardrails: unsubscribe rate, spam complaints

Hand to A/B Test Designer.

## Output artifact

`reengagement-campaign.md` with:

- Tiers + rules
- Flow diagram (mermaid)
- Per-message copy
- Exit conditions
- Metrics spec

## Handoff

- Wake-up users → Welcome Sequencer (returning-user track)
- Unsubscribes / high complaint rates → feed back to Cohort & Churn Analyzer (maybe the product broke, not just the user)

## Example call

> "Design a win-back for our ~8,000 users who haven't logged in in 45+ days. Email-only. Offer is a 30-day free extension on Pro. Target: 10% wake-up rate, < 0.5% spam complaint."
