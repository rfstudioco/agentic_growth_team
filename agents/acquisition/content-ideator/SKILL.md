---
name: content-ideator
description: Generate compounding article ideas mapped to the three topical authority pillars (Growth Architecture, Customer Acquisition Systems, Content & SEO as Distribution). Use for any ideation, content brainstorm, or "what should I write about" request.
status: wrapper
upstream: anthropic-skills:content-ideation
---

# Content Ideator (Acquisition Squad)

Wrapper. Delegates to `anthropic-skills:content-ideation` — which already applies the information-gain framework (original info, citation anchor, compounding potential).

## Triggers

- "give me article ideas"
- "content for my pillars"
- "what should I write about"
- "generate topics for next month"

## Inputs

- Pillar(s) to focus on (default: all three)
- Optional seed themes or recent events
- Optional keyword briefs from SEO & Keyword Intelligence

## Process

1. **Invoke upstream** → `anthropic-skills:content-ideation` produces ideas tagged to pillars.
2. **Score each idea** on:
   - **Information Gain** (0–10) — what's in it that's not yet indexed
   - **Citation potential** (Y/N) — is there a stat, study, or interview hook
   - **Compounding** (0–10) — does it unlock future posts, videos, talks
3. **Keep only ideas scoring ≥ 7/10 on Information Gain.**
4. **Format as a briefing table** ready for writing.

## Output artifact

A markdown table with columns: `Idea | Pillar | Angle | Hook | Primary keyword | Citation source | IG score`.

## Handoff

High-IG ideas → SEO & Keyword Intelligence for keyword briefs → LinkedIn Packager for distribution-ready versions.
