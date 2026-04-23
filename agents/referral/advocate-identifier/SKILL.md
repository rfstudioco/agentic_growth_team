---
name: advocate-identifier
description: Score and rank your user base on advocacy potential (NPS × usage × tenure) and produce a ranked outreach queue with personalized ask messages. Use when the user says "find our advocates", "who should we ask for referrals", "top champions", or is launching a referral / case-study / community play.
status: new
---

# Advocate Identifier (Referral Squad)

Turns your user base into a ranked list of champions ready to be asked — for a case study, a referral, a quote, a panel, or beta feedback.

## Triggers

- "who are our advocates"
- "find our champions"
- "build an advocacy list"
- "who should we ask for referrals"
- "NPS × usage scoring"

## Inputs required

1. **NPS responses** with user IDs (most recent per user)
2. **Usage data** — logins, feature use, tenure
3. **Account attributes** — plan, company size, public profile (LinkedIn, Twitter)
4. **Relationship signals** — has a CSM? ever replied to a founder email? posted about us on social?
5. **Outreach inventory** — what are we actually asking for? (case study, reference call, referral, testimonial, beta)

## Process

### Step 1 — Compute the advocacy score

For each user:

```
Advocacy score = 0.4 × NPS_norm + 0.3 × Usage_norm + 0.15 × Tenure_norm
               + 0.1 × Relationship_signals + 0.05 × Public_profile_reach
```

Normalization: 0–100. Include only users with NPS ≥ 8 AND tenure ≥ 90 days AND active in last 30 days.

### Step 2 — Segment advocates by what they're best for

Not every advocate is right for every ask. Bucket them:

- **Case study ready** — high usage + concrete use case + willing to be public
- **Quote-givers** — gave a great NPS comment but may not want long engagement
- **Referrers** — high-NPS prosumer-types with active networks (LinkedIn followers, Twitter reach)
- **Beta testers** — power users who file good bug reports
- **Speakers / panelists** — public profile + happy to talk

Tag each advocate with the top 1–2 buckets they fit.

### Step 3 — Write the ask

For each advocate × ask type, produce a short, specific, first-name outreach message:

- Reference something they specifically said or did (pull from NPS comment or usage)
- Be concrete about the ask (not "let's chat")
- Be concrete about what they get in return (early access, exposure, a t-shirt, $50 donation, nothing but gratitude)
- Make it one-click to say yes or no

Keep each message under 80 words.

### Step 4 — Rate-limit the outreach

Rules:

- Max 1 ask per advocate per 60 days
- Never cold-ask a user with an open support ticket
- Always route through CSM if they have one
- Don't ask enterprise accounts without account team sign-off

### Step 5 — Output the queue

CSV with columns:

```
user_id | name | email | company | score | best_for | suggested_ask | owner | status
```

Plus a markdown file with the top 20 messages pre-written, ready to paste.

## Output artifacts

- `advocate-queue.csv`
- `advocate-outreach-top20.md`

## Handoff

- Case-study candidates → Case Study Builder
- Referrers → Referral Program Designer (invite to beta program first)
- Quote-givers → Landing Page Optimizer + Competitive Scout
- Performance of outreach → Performance Reporter

## Example call

> "Build our advocate list. I've attached NPS responses (users.csv), usage (events.csv), and plan/tenure (accounts.csv). We want: 5 case study candidates, 20 referrers, 10 quote-givers for the new homepage."
