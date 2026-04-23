# 🎯 Acquisition Squad

**Mission:** Generate qualified demand. Turn strangers into known leads.

**North-star metric:** Qualified leads / month (MQLs that match ICP).
**Guardrails:** CAC payback < 12 months, lead → SAL conversion > 20%.

## Agents in this squad

| Agent | Upstream | What it produces |
|---|---|---|
| [icp-researcher](./icp-researcher/SKILL.md) | `design:user-research` | ICP one-pager + anti-ICP list |
| [seo-keyword-intelligence](./seo-keyword-intelligence/SKILL.md) | `marketing:seo-audit` | Keyword map + content-gap report |
| [content-ideator](./content-ideator/SKILL.md) | `anthropic-skills:content-ideation` | Pillar-mapped article ideas with citations |
| [competitive-scout](./competitive-scout/SKILL.md) | `marketing:competitive-brief` | Positioning brief + battlecard |
| [paid-ads-generator](./paid-ads-generator/SKILL.md) | **new** | 20 ad variants laddered by angle |
| [landing-page-optimizer](./landing-page-optimizer/SKILL.md) | **new** | Annotated audit + rewritten copy |
| [linkedin-packager](./linkedin-packager/SKILL.md) | `anthropic-skills:linkedin-article` | Publish-ready LinkedIn article (.docx) |

## Typical chain

```
icp-researcher → content-ideator → seo-keyword-intelligence
                                        ↓
                            landing-page-optimizer
                                        ↓
                         paid-ads-generator + linkedin-packager
```

## Handoff contract to Activation

Acquisition delivers leads tagged with:
- Segment (from ICP)
- Source (campaign / keyword / ad variant)
- First-touch content
- Intent score (0–100)

Activation picks them up inside the Welcome Sequencer.
