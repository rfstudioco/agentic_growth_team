---
name: seo-keyword-intelligence
description: Keyword research, site audit, content-gap analysis, and a prioritized SEO action plan. Use when the user says "SEO audit", "keyword research", "find content gaps", "why isn't our site ranking", or is planning organic growth.
status: wrapper
upstream: marketing:seo-audit
---

# SEO & Keyword Intelligence (Acquisition Squad)

Wrapper. Delegates to `marketing:seo-audit` and adds growth-specific layering (pillar alignment + funnel-stage tagging).

## Triggers

- "run an SEO audit"
- "find keywords we can rank for"
- "content gaps vs. competitor X"
- "prioritize our SEO backlog"

## Inputs

- Domain URL
- 2–3 competitor domains
- List of ranking pages (optional — will crawl if missing)
- Your 3 content pillars (from Content Ideator or ICP)

## Process

1. **Run the upstream audit** → invoke `marketing:seo-audit` for technical health, keyword opportunities, and content gaps.
2. **Tag every keyword** with:
   - **Funnel stage** (TOFU / MOFU / BOFU)
   - **Pillar** (which of your 3 authority pillars it feeds)
   - **Intent** (informational / navigational / commercial / transactional)
3. **Prioritize** using the IG-score: Intent × Gap × Effort-inverse. Split into:
   - Quick wins (< 4 weeks, existing pages)
   - Strategic bets (new pillar content, > 90 days)
4. **Output a keyword map** with owner + due date columns ready for Content Ideator to brief.

## Output artifact

`seo-plan.md` + `keyword-map.xlsx` (via `anthropic-skills:xlsx`).

## Handoff

Passes keyword briefs into Content Ideator. Flags technical issues to eng backlog.
