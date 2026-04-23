---
name: onboarding-designer
description: Design a first-run onboarding flow that gets a signup to their activation event in the fewest steps, with instrumentation so each step is measurable. Use when the user says "design onboarding", "redo our signup flow", "reduce time-to-value", or is launching a new product.
status: new
---

# Onboarding Designer (Activation Squad)

Maps signup → aha. Outputs a step-by-step flow, a copy brief, and a metrics spec so you can measure each step.

## Triggers

- "design our onboarding flow"
- "redo signup"
- "reduce time-to-value"
- "onboarding funnel is leaky"
- "plan the first-run experience"

## Inputs required

1. **Activation event** — defined by Aha-Moment Mapper (if missing, call that agent first)
2. **Current flow** — screenshots, screen recording, or description
3. **Current D1 and D7 activation rates** (if known)
4. **User type** — self-serve, sales-assisted, or both
5. **Tech constraints** — what the team can realistically build in 4 weeks

## Process

### Step 1 — Articulate the goal in one sentence

> "Get <user type> from signup to <activation event> in ≤ <target time>."

Example: "Get solo founders from signup to publishing their first page in ≤ 8 minutes."

### Step 2 — Map the minimum viable path

List **every step** a user currently takes from landing page → activation. For each step:

- Is it necessary for activation? (if no → cut it)
- Does the user need to think? (if yes → can it be a default?)
- Does it block on the user waiting for something? (if yes → can it run async?)

The answer to "minimum viable path" is almost always fewer than 5 interactions.

### Step 3 — Design the flow

Produce a flow with these canonical stages:

1. **Signup** — email/SSO only; no profile upfront
2. **Orient** — one screen answering "what am I about to do?"
3. **Do the thing** — the aha-adjacent action, scaffolded
4. **See the thing** — explicit moment where value is visible
5. **Commit** — save/publish/share so it's sticky
6. **Invite** — team/collaborator (if product benefits)

For each stage, specify:

- Screen / surface
- Primary action
- Microcopy brief (hand to UX Copy Writer)
- Empty state behavior
- Skippable? (if yes, what happens to skippers)

### Step 4 — Add activation safety nets

- **Progressive profiling** — ask for profile data _after_ first value, not before
- **Milestone celebration** — explicit UI for "you just did the thing"
- **Stall detection** — if user drops without completing step X, trigger Welcome Sequencer email

### Step 5 — Write the instrumentation spec

List every event that must be tracked, with:

- Event name (`signup_completed`, `aha_event_completed`, `step_X_skipped`)
- Properties (`user_id`, `plan`, `source`, `variant`)
- Funnel view this event feeds
- Success rate target

Hand to Attribution Mapper + Growth Dashboard Builder.

### Step 6 — Declare metric targets

- Target D1 activation rate
- Target median time-to-activation
- Guardrail: signup rate must not drop more than 5pp

## Output artifact

`onboarding-design.md` with:

- Goal statement
- Flow diagram (mermaid)
- Per-step spec
- Copy brief
- Events spec
- Targets
- 2-week rollout plan

## Handoff

- Copy brief → UX Copy Writer
- Events spec → Attribution Mapper + eng
- Stall detection → Welcome Sequencer
- Metric targets → A/B Test Designer (to run the launch as a test)

## Example call

> "Our signup-to-first-page-published rate is 32% over 7 days. Help me redesign the flow. The activation event is publishing a page. Our current flow is [screenshots attached]. Target self-serve users."
