# Team Structure

The Agentic Growth Team is organized around the **AARRR funnel** (Dave McClure's Pirate Metrics) with a cross-functional **Data Ops & Experimentation** squad that serves every other squad.

```
                      ┌────────────────────────────────────┐
                      │      CLAUDE GROWTH TEAM            │
                      │      28 agents · 6 squads          │
                      └──────────────┬─────────────────────┘
                                     │
      ┌──────────┬──────────┬────────┼────────┬──────────┬──────────┐
      ▼          ▼          ▼        ▼        ▼          ▼          ▼
  Acquisition Activation Retention Revenue Referral   Data Ops
    (7)        (4)         (5)       (5)      (3)       (4)
```

---

## 🎯 Acquisition Squad — _generate qualified demand_

Turns strangers into known leads. Owns top-of-funnel across SEO, paid, social, and competitive positioning.

| # | Agent | One-liner | Status |
|---|---|---|---|
| 1 | [ICP Researcher](./agents/acquisition/icp-researcher/SKILL.md) | Builds a falsifiable Ideal Customer Profile from interviews, data, and competitor signals. | existing |
| 2 | [SEO & Keyword Intelligence](./agents/acquisition/seo-keyword-intelligence/SKILL.md) | Keyword research, site audit, content gap analysis. | existing |
| 3 | [Content Ideator](./agents/acquisition/content-ideator/SKILL.md) | Generates compounding article ideas mapped to your authority pillars. | existing |
| 4 | [Competitive Scout](./agents/acquisition/competitive-scout/SKILL.md) | Positioning gaps, messaging angles, battlecards. | existing |
| 5 | [Paid Ads Generator](./agents/acquisition/paid-ads-generator/SKILL.md) | Hook/body/CTA variants for Meta, LinkedIn, Google, with angle laddering. | **new** |
| 6 | [Landing Page Optimizer](./agents/acquisition/landing-page-optimizer/SKILL.md) | Audits a page and rewrites for message-match, scannability, and conversion. | **new** |
| 7 | [LinkedIn Packager](./agents/acquisition/linkedin-packager/SKILL.md) | Turns raw content into SEO-optimized LinkedIn articles. | existing |

## ⚡ Activation Squad — _get first-time users to "aha" fast_

Owns the first 7 days of the user lifecycle. Measures time-to-value.

| # | Agent | One-liner | Status |
|---|---|---|---|
| 8 | [Onboarding Designer](./agents/activation/onboarding-designer/SKILL.md) | Maps signup → aha in the fewest steps, with checkpoint metrics. | **new** |
| 9 | [UX Copy Writer](./agents/activation/ux-copy-writer/SKILL.md) | Microcopy, empty states, error messages, CTAs. | existing |
| 10 | [Welcome Sequencer](./agents/activation/welcome-sequencer/SKILL.md) | 5–7 email welcome series with branching + exit conditions. | existing |
| 11 | [Aha-Moment Mapper](./agents/activation/aha-moment-mapper/SKILL.md) | Identifies the activation event from usage data + interviews. | **new** |

## 🔁 Retention Squad — _keep users engaged, reduce churn_

Owns weeks 2–∞. Measures D7/D30 retention, churn, and expansion triggers.

| # | Agent | One-liner | Status |
|---|---|---|---|
| 12 | [Lifecycle Email Designer](./agents/retention/lifecycle-email-designer/SKILL.md) | Ongoing drip, tips, milestone emails past onboarding. | existing |
| 13 | [Cohort & Churn Analyzer](./agents/retention/cohort-churn-analyzer/SKILL.md) | Runs cohort retention curves; surfaces churn drivers. | **new** |
| 14 | [NPS Synthesizer](./agents/retention/nps-synthesizer/SKILL.md) | Turns NPS / survey text into themes, segments, and actions. | existing |
| 15 | [Re-engagement Campaigner](./agents/retention/reengagement-campaigner/SKILL.md) | Win-back flows for dormant users with channel fallback. | **new** |
| 16 | [Feature Adoption Tracker](./agents/retention/feature-adoption-tracker/SKILL.md) | Monitors adoption of key features; nudges non-adopters. | **new** |

## 💰 Revenue Squad — _convert, upsell, maximize LTV_

Owns paid conversion, pricing page, checkout, and expansion revenue.

| # | Agent | One-liner | Status |
|---|---|---|---|
| 17 | [Pricing Page Optimizer](./agents/revenue/pricing-page-optimizer/SKILL.md) | Audits plan structure, anchoring, feature matrix, CTA. | **new** |
| 18 | [Checkout Funnel Auditor](./agents/revenue/checkout-funnel-auditor/SKILL.md) | Finds friction in trial-to-paid and paid checkout flows. | **new** |
| 19 | [Trial-to-Paid Converter](./agents/revenue/trial-to-paid-converter/SKILL.md) | Drip + in-app nudges for trialists; personalized by usage. | **new** |
| 20 | [Upsell Sequencer](./agents/revenue/upsell-sequencer/SKILL.md) | Triggers upgrades based on usage signals; writes the emails. | **new** |
| 21 | [Revenue Dashboard Builder](./agents/revenue/revenue-dashboard-builder/SKILL.md) | MRR, churn, ARPU, LTV dashboard. | existing |

## 📣 Referral Squad — _turn customers into distribution_

Owns virality, advocacy, and case-study flywheel.

| # | Agent | One-liner | Status |
|---|---|---|---|
| 22 | [Referral Program Designer](./agents/referral/referral-program-designer/SKILL.md) | Double-sided incentives, mechanics, tracking spec. | **new** |
| 23 | [Case Study Builder](./agents/referral/case-study-builder/SKILL.md) | Interview → narrative case study with metrics + quotes. | **new** |
| 24 | [Advocate Identifier](./agents/referral/advocate-identifier/SKILL.md) | Scores your user base for NPS × usage to find champions. | **new** |

## 📊 Data Ops & Experimentation — _serves every squad_

Cross-functional. Owns experimentation rigor, attribution, and weekly/monthly reporting.

| # | Agent | One-liner | Status |
|---|---|---|---|
| 25 | [A/B Test Designer](./agents/data-ops/ab-test-designer/SKILL.md) | Hypothesis, sample size, primary/guardrail metrics, analysis plan. | **new** |
| 26 | [Attribution Mapper](./agents/data-ops/attribution-mapper/SKILL.md) | Builds multi-touch attribution model from raw events. | **new** |
| 27 | [Growth Dashboard Builder](./agents/data-ops/growth-dashboard-builder/SKILL.md) | Self-contained HTML dashboard with KPIs + filters. | existing |
| 28 | [Performance Reporter](./agents/data-ops/performance-reporter/SKILL.md) | Weekly/monthly stakeholder report with wins, misses, next bets. | existing |

---

## How the squads interact

- **Acquisition** feeds leads into **Activation**.
- **Activation** hands active users to **Retention**.
- **Retention** flags expansion-ready users for **Revenue**.
- **Revenue** identifies happy payers for **Referral**.
- **Data Ops** instruments and reports across all four.

Every handoff has an owning agent — see each squad's `README.md` for the contract.
