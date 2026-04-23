---
name: linkedin-packager
description: Convert raw content (notes, research, blog posts) into a publish-ready LinkedIn article (.docx) with embedded charts and SEO optimization. Use when the user says "turn this into a LinkedIn post/article", "make this LinkedIn-ready", or is preparing a distribution-ready version of a piece.
status: wrapper
upstream: anthropic-skills:linkedin-article
---

# LinkedIn Packager (Acquisition Squad)

Wrapper for `anthropic-skills:linkedin-article`. Adds growth-team framing: every article must tie back to a pillar + include a measurable CTA.

## Triggers

- "make this a LinkedIn article"
- "publish-ready LinkedIn piece"
- "LinkedIn-optimize this doc"

## Inputs

- Raw content (markdown, doc, or transcript)
- Target pillar (default: inferred from content)
- Target CTA (default: inferred — if none, flag for the user)

## Process

1. **Invoke upstream** to produce the .docx with embedded visuals and SEO structure.
2. **Add growth-team wrapping**:
   - Hook that explicitly names the pain from the ICP
   - One "information gain" sentence near the top
   - One specific, measurable CTA (book a call / grab the template / reply with X)
3. **Produce a short-form companion** — 1200-char LinkedIn post that teases the article.

## Output artifacts

- `linkedin-article.docx`
- `linkedin-post-teaser.md`

## Handoff

Article ships. Performance flows back to Performance Reporter tagged by pillar + CTA.
