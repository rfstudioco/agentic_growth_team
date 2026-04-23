# Agentic Growth Team
## 28 AI Agents for your AARRR funnels

> A modular, AARRR-aligned team of Claude agents that runs your growth org.
> Inspired by the Claude Fundraising Team pattern — purpose-built for growth marketers, founders, and solo operators who want leverage without hiring.

![Version: 0.1.0](https://img.shields.io/badge/version-0.1.0-blue)

---

## Access Gate

**This repository is private and distributed invite-only.**

You're reading this because you were given access by the maintainer (RFStudio). Please do not fork, mirror, redistribute, or post excerpts publicly without written permission.

To request access or collaborate:

- Email: **growth@rfstudio.co**
- Put `Claude Growth Team — access request` in the subject line
- Include: your name, company, what you'd use it for, and who referred you

Access is granted case-by-case. Read [ACCESS.md](./ACCESS.md) for the full policy and [LICENSE.md](./LICENSE.md) for usage terms.

---

## What this is

The Claude Growth Team is a coordinated set of 28 Claude agents (skills) organized around the **AARRR funnel** — Acquisition, Activation, Retention, Revenue, Referral — plus a cross-functional **Data Ops & Experimentation** squad.

Each agent is a real, installable Claude skill with a `SKILL.md` file that defines:

- when it should trigger
- what inputs it needs
- the step-by-step process it runs
- the artifacts it produces
- worked examples

Agents are composable. You can run them individually (`"audit my pricing page"`) or chain them into campaigns (`ICP Researcher → Content Ideator → Landing Page Optimizer → Welcome Sequencer`).

## Team at a glance

| Squad | Mission | Agents |
|---|---|---|
| 🎯 **Acquisition** | Generate qualified demand | 7 |
| ⚡ **Activation** | Get first-time users to "aha" fast | 4 |
| 🔁 **Retention** | Keep users engaged, reduce churn | 5 |
| 💰 **Revenue** | Convert, upsell, maximize LTV | 5 |
| 📣 **Referral** | Turn customers into distribution | 3 |
| 📊 **Data Ops** | Experiments, attribution, reporting | 4 |
| | **Total** | **28** |

Full org chart: [team-structure.md](./team-structure.md)
Existing vs. new skill map: [skills-map.md](./skills-map.md)

## Repo layout

```
claude_growth_team/
├── README.md                  ← you are here
├── ACCESS.md                  ← access policy & gate rules
├── LICENSE.md                 ← proprietary, invite-only
├── team-structure.md          ← full org chart w/ agent descriptions
├── skills-map.md              ← which agents use existing skills vs. new
└── agents/
    ├── acquisition/           ← 7 agents
    ├── activation/            ← 4 agents
    ├── retention/             ← 5 agents
    ├── revenue/               ← 5 agents
    ├── referral/              ← 3 agents
    └── data-ops/              ← 4 agents
```

## How to use an agent

Every agent lives at `agents/<squad>/<agent-name>/SKILL.md`. To use one:

1. **Install** — copy the agent folder into your Claude plugin or skills directory.
2. **Trigger** — say one of the phrases listed in the agent's `## Triggers` section (e.g., "run a churn cohort analysis", "design a referral program").
3. **Provide inputs** — the agent will ask for what it needs (or pull from context).
4. **Ship the output** — every agent produces a concrete artifact (doc, sheet, dashboard, email copy, spec).

## Running the whole team

The most common campaign chain:

```
ICP Researcher
   ↓
Content Ideator → SEO & Keyword Intelligence
   ↓
Landing Page Optimizer + Paid Ads Generator
   ↓
Welcome Sequencer → Onboarding Designer → Aha-Moment Mapper
   ↓
Lifecycle Email Designer → Feature Adoption Tracker
   ↓
Trial-to-Paid Converter → Upsell Sequencer
   ↓
Case Study Builder → Referral Program Designer
   ↓
Performance Reporter + A/B Test Designer (always-on)
```

## Versioning

- `0.1.0` — initial team + 28 agents (Apr 2026)
- Roadmap: community-pulse analyzer, exclusion list manager, growth-loop designer

## Maintained By

RFStudio — **growth@rfstudio.co**

Built by chaining Claude skills. Not affiliated with Anthropic beyond being a user.
