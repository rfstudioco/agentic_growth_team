---
name: cohort-churn-analyzer
description: Run cohort retention curves and churn-driver analysis on user/subscription data; surface the biggest drop-off weeks and the user traits that predict churn. Use when the user says "run cohort analysis", "why are users churning", "retention curve", or "find the churn drivers".
status: new
---

# Cohort & Churn Analyzer (Retention Squad)

Produces the three artifacts every retention conversation needs: cohort curve, churn driver table, and a "save list" of at-risk users.

## Triggers

- "run a cohort analysis"
- "why are users churning"
- "build our retention curve"
- "find the churn drivers"
- "at-risk user list"

## Inputs required

1. **Event data or subscription export** — enough to derive sign-up date, last-active date, churn date, plan
2. **Churn definition** — days-inactive threshold or explicit cancel event
3. **User attributes** — plan, acquisition source, company size, any feature-usage flags
4. **Time range** — default: last 12 cohorts (monthly)

## Process

### Step 1 — Build the cohort curve

Group users by signup month. For each cohort, compute retention at week 1, 2, 4, 8, 12, 24. Output the classic cohort triangle.

Flag:

- **Cliff weeks** — where > 15pp retention is lost in a single week
- **Flattening point** — week at which the curve stabilizes (your "sticky rate")
- **Cohort-over-cohort trend** — are newer cohorts retaining better or worse

### Step 2 — Segment the curve

Repeat Step 1 by:

- Plan
- Acquisition source
- Activation status (activated vs. not — from Aha-Moment Mapper)
- Company size band

Find the segment with the **widest spread**. That's where the leverage is.

### Step 3 — Identify churn drivers

For users who churned, compare their pre-churn behavior to retained users. Run:

- Feature-usage diff (which features do retained users touch that churned don't)
- Time-to-aha comparison (did churners miss activation entirely?)
- Support-ticket volume
- Last NPS score if available

Rank the top 5 driver hypotheses by effect size + reach.

### Step 4 — Survival-ish analysis (lightweight)

For each driver, estimate: "if we moved every user from low-usage to high-usage of feature X, what would W12 retention become?" Use a basic uplift estimate; flag confidence honestly.

### Step 5 — Build the save list

Produce a ranked list of currently-active users whose behavior matches the "about to churn" pattern. Include:

- User ID, plan, last-active date
- Risk score (0–100)
- Which driver(s) they match
- Recommended intervention (from the Re-engagement Campaigner playbook)

### Step 6 — Write the report

Produce:

- Cohort triangle visual
- 2–3 segmented curves showing the widest spreads
- Churn-driver table with effect sizes
- Save list with suggested interventions

## Output artifacts

- `cohort-analysis.html` (interactive chart) via `data:create-viz`
- `churn-drivers.md`
- `save-list.csv`

## Handoff

- Save list → Re-engagement Campaigner (interventions) + Feature Adoption Tracker (nudges)
- Driver hypotheses → A/B Test Designer to validate
- Cohort curve → Performance Reporter + Growth Dashboard Builder

## Example call

> "Run a cohort analysis on users.csv + events.csv. Churn = no login for 30 days. I want to see if our Pro plan retains better than our Team plan and what features predict retention."
