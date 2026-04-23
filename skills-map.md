# Skills Map — Composed vs. Core

Each agent in the Agentic Growth Team is either **composed** by wrapping a pre-existing, publicly available skill (like those in Anthropic's skill library) or is a **core** skill written from scratch for this project.

## Summary (Based on original Claude implementation)

- **Composed Agents:** 12 agents are thin wrappers around 7 unique upstream skills.
- **Core Agents:** 16 agents are net-new, with their methodology defined entirely within this project.

## Example: Composed Agents (from Claude skill library)

| Agent | Upstream skill | Squad |
|---|---|---|
| ICP Researcher | `design:user-research` | Acquisition |
| SEO & Keyword Intelligence | `marketing:seo-audit` | Acquisition |
| Content Ideator | `anthropic-skills:content-ideation` | Acquisition |
| Competitive Scout | `marketing:competitive-brief` | Acquisition |
| LinkedIn Packager | `anthropic-skills:linkedin-article` | Acquisition |
| UX Copy Writer | `design:ux-copy` | Activation |
| Welcome Sequencer | `marketing:email-sequence` | Activation |
| Lifecycle Email Designer | `marketing:email-sequence` | Retention |
| NPS Synthesizer | `design:research-synthesis` | Retention |
| Revenue Dashboard Builder | `data:build-dashboard` | Revenue |
| Growth Dashboard Builder | `data:build-dashboard` | Data Ops |
| Performance Reporter | `marketing:performance-report` | Data Ops |

Each of these agents' `SKILL.md` acts as a **lean wrapper** that:

1. Declares growth-specific triggers (e.g., "run an ICP research sprint")
2. Adds growth-specific inputs & constraints (e.g., must produce a falsifiable hypothesis, must tag segments by ARR band)
3. Delegates the core method to the upstream skill
4. Adds growth-specific output shape (e.g., ICP one-pager, campaign brief)

## Core Agents (New Skills)

These were authored from scratch as they represent highly growth-specific workflows not found in general-purpose skill libraries.

| # | Agent | Squad | Why new |
|---|---|---|---|
| 1 | Paid Ads Generator | Acquisition | No existing skill for multi-platform ad variant generation with angle laddering |
| 2 | Landing Page Optimizer | Acquisition | No dedicated page-audit + rewrite skill |
| 3 | Onboarding Designer | Activation | Combines flow design + metric instrumentation not found elsewhere |
| 4 | Aha-Moment Mapper | Activation | Specific methodology (usage data + interviews) for activation event detection |
| 5 | Cohort & Churn Analyzer | Retention | Cohort curves + survival analysis as a packaged workflow |
| 6 | Re-engagement Campaigner | Retention | Dormant-user specific with channel fallback logic |
| 7 | Feature Adoption Tracker | Retention | Adoption scoring + nudge generation loop |
| 8 | Pricing Page Optimizer | Revenue | Pricing-specific audit framework |
| 9 | Checkout Funnel Auditor | Revenue | Funnel friction detection w/ specific heuristics |
| 10 | Trial-to-Paid Converter | Revenue | Usage-personalized conversion playbook |
| 11 | Upsell Sequencer | Revenue | Signal-triggered expansion revenue motion |
| 12 | Referral Program Designer | Referral | Incentive math + mechanics spec |
| 13 | Case Study Builder | Referral | Interview-to-published-case-study pipeline |
| 14 | Advocate Identifier | Referral | NPS × usage scoring + outreach queue |
| 15 | A/B Test Designer | Data Ops | Prescriptive test design with power calc + guardrails |
| 16 | Attribution Mapper | Data Ops | Multi-touch model-from-events workflow |

(16 new SKILL.md files — some squads have more than one new agent; Retention and Revenue are new-heavy because the ecosystem skills lean marketing-generic.)

## Coverage table

| Squad | Total | Existing | New |
|---|---|---|---|
| Acquisition | 7 | 5 | 2 |
| Activation | 4 | 2 | 2 |
| Retention | 5 | 2 | 3 |
| Revenue | 5 | 1 | 4 |
| Referral | 3 | 0 | 3 |
| Data Ops | 4 | 2 | 2 |
| **Total** | **28** | **12** | **16** |

## Why the split matters

- **Speed** — 12 agents work today by composing skills that already ship with Claude/Anthropic plugins.
- **Originality** — the 16 new agents are where this team differentiates. Growth-specific methodology, not generic marketing.
- **Maintainability** — when upstream skills improve, the 12 "wrapper" agents inherit those upgrades for free.
