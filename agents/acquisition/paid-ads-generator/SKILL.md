---
name: paid-ads-generator
description: Generate paid ad variants (hook/body/CTA) for Meta, LinkedIn, Google, and X with an angle ladder and platform-aware formatting. Use when the user says "write ad copy", "generate ads for <platform>", "we need ad variants", "angle test", or is launching / refreshing a paid campaign.
status: new
---

# Paid Ads Generator (Acquisition Squad)

Produces ad creative at the variant level — multiple angles × platforms × audiences — in one run, with an angle ladder so you can test hypotheses instead of random copy.

## Triggers

- "write ad copy for <platform>"
- "generate Meta / LinkedIn / Google ads"
- "angle test for <campaign>"
- "we need 20 ad variants"
- "refresh our creative"

## Inputs required

Ask for each (or infer from context):

1. **Product / offer** — what is being promoted, in one sentence
2. **ICP segment** — from ICP Researcher (role, firmographics, pain)
3. **Platforms** — Meta, LinkedIn, Google Search, Google Display, X, TikTok
4. **Unclaimed angles** — from Competitive Scout (optional but high-leverage)
5. **Funnel stage** — cold / warm / retargeting
6. **Brand voice** — tone sample or link to brand-review guidelines
7. **Claims to avoid** — legal/compliance no-go list
8. **Desired count** — default 20 variants (5 angles × 4 platforms)

## Process

### Step 1 — Build the angle ladder (5 angles)

Every campaign gets 5 angles laddered from direct to lateral:

| Angle | Hook template |
|---|---|
| Pain-amplification | "If you're still <old-way>, you're losing <cost>." |
| Benefit-forward | "Here's how to <outcome> without <tradeoff>." |
| Proof / social | "<N> teams at <familiar-companies> use this for <result>." |
| Contrarian | "Everyone says <conventional>. It's wrong. Here's what works." |
| Story / curiosity | "I spent <time> on <thing>. Here's what I learned." |

Pick angles that best match the ICP's current belief state (from ICP Researcher).

### Step 2 — Generate per-platform variants

For each angle × platform, produce:

- **Hook / first line** — platform-specific character limit
- **Body** — benefit or story
- **CTA** — platform-native button text
- **Visual brief** — one sentence describing the static/video that should accompany

Platform constraints to respect:

- **Meta:** 40-char headline, 125-char primary text for most placements
- **LinkedIn:** 150-char intro, 600-char body sweet spot; B2B tone
- **Google Search:** 30-char headline × 3, 90-char description × 2
- **Google Display:** 5 headlines (30 char), 5 descriptions (90 char), 1 long headline (90 char)
- **X:** 280 chars including link
- **TikTok:** 100 chars, hook in first 3 seconds

### Step 3 — Score each variant

Score on:

- **Hook strength** (does it stop the scroll in < 2 seconds?)
- **Message-match** (does it match the landing page?)
- **Differentiation** (is this claimable only by us?)

Keep variants scoring ≥ 7/10 on all three. Rewrite weak ones.

### Step 4 — Output

Deliver a table with columns:

```
| Angle | Platform | Headline | Body | CTA | Visual brief | Audience | Notes |
```

And a short **test plan**: which variant is the control, which are the learning bets, and what each variant tests.

## Output artifact

`paid-ads-<campaign>.md` + optionally `paid-ads.xlsx` for bulk upload templates.

## Handoff

- Variants with message-match issues → Landing Page Optimizer to fix the page
- Test plan → A/B Test Designer to formalize sample size + stop rule
- Performance results → Performance Reporter

## Example call

> "Generate 20 ad variants for our ICP (mid-market RevOps leaders at 200–2000-person SaaS) for a webinar on closing the pipeline coverage gap. Platforms: Meta + LinkedIn. Use the 'everyone says more leads, it's coverage quality' angle from the competitive scout."
