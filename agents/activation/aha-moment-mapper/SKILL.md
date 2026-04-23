---
name: aha-moment-mapper
description: Identify the single best activation event for a product by correlating usage data with retention and triangulating with user interviews. Use when the user says "what's our aha moment", "define activation", "which event predicts retention", or is setting up a North Star metric.
status: new
---

# Aha-Moment Mapper (Activation Squad)

Finds the one event that most strongly predicts long-term retention for your product. Blends quantitative (event data) and qualitative (interviews) signals.

## Triggers

- "what's our aha moment"
- "define activation for us"
- "which event predicts retention"
- "set up our North Star metric"
- "find the 'Facebook 7 friends in 10 days' for us"

## Inputs required

1. **Event data** — at least 60 days of user event logs with timestamps, user IDs, event names
2. **Retention definition** — what counts as retained (e.g., "used product in week 4")
3. **3–5 interviews** with retained users (recordings or transcripts)
4. **Candidate events** — product team's best guesses (optional; we'll generate our own too)

## Process

### Step 1 — Quantitative side: find predictive events

For every event in the dataset:

1. Split users into cohorts by whether they performed event E in first N days (N = 1, 3, 7).
2. Compute retention at day 30 for each cohort.
3. Record the retention **lift** and the **statistical significance** (chi-squared or Fisher's).
4. Also record the event's **reachability** — what % of signups ever do it.

The candidate aha event is high-lift AND high-reachability. Something only 2% of users do isn't a viable activation target even if it predicts retention perfectly.

### Step 2 — Apply the frequency/magnitude lens

The strongest activation events are usually of the form:

> "Did <core action> <N> times within <T> days"

Test several thresholds (N, T) and surface the combo with the cleanest retention cliff.

### Step 3 — Qualitative side: interview validation

From the interviews, pull quotes matching:

- "The moment I got it was when..."
- "I started using it regularly after..."
- "I almost gave up, but then..."

See if these moments align with the quantitative candidate. If they don't, something is wrong — usually either instrumentation or the real moment is upstream of what you're measuring.

### Step 4 — Write the activation definition

Format:

> **Activation event:** <action verb + object>, done at least <N> times within <T> days of signup.
>
> **Why this event:** <retention lift>pp vs. non-activators, reached by <X>% of signups.
>
> **Interview evidence:** <2–3 quote snippets>.

### Step 5 — Specify the instrumentation

List the event schema (name, properties, triggering conditions) for eng. Hand to Attribution Mapper + Growth Dashboard Builder so it shows up on the dashboard from day one.

### Step 6 — Set a target

- Current % of signups activated
- 90-day target
- Owner (usually Activation squad lead)

## Output artifact

`aha-moment.md` with:

- Candidate events scored
- The chosen event with rationale
- Interview evidence
- Instrumentation spec
- Targets + owner

## Handoff

- Activation definition → Onboarding Designer (the thing to optimize for)
- Instrumentation spec → eng + Attribution Mapper
- Target → Growth Dashboard Builder + Performance Reporter

## Example call

> "Help me find our aha moment. I've exported 90 days of events to events.csv. Retention means 'logged in during week 4 post-signup'. Here are 5 interview transcripts with retained users."
