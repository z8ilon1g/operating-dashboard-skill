# Operating Dashboard Skill

> A two-stage methodology for building management dashboards that can actually be used in a decision meeting.
> The skill instructions are written in Chinese (as the target users and the original practice are Chinese-speaking); this file is a short orientation in English.

[中文说明](README.md) · [MIT License](LICENSE)

---

## The problem

Most dashboards fail not because the charts are ugly, but because **the chart, the caption and the source table do not come from the same number**. This skill fixes that by forcing the order:

1. **Design stage** — settle the period/scope conventions first, derive metrics from the business main chain, build one table per screen, then choose the visual form and produce the data tables.
2. **Build stage** — write an eight-field per-screen spec, build in small batches (yourself in SVG/front-end code, or by instructing a Feishu/Coze-style agent), gate every batch on a receipt with measured values, then run the acceptance checklist.

## Eleven hard rules (excerpt)

- Conventions before data. No chart until the conventions are signed off.
- Every segment gets its **own denominator**; never share one target across segments.
- Never split a total row across details. Unknown means "to be extracted", not a pro-rated guess.
- Blank ≠ 0. Draw a placeholder skeleton instead of estimating.
- Selling price is not cost — never back out inventory value from price.
- Write down the as-of date for every snapshot.
- Captions must be derivable from the data array; hand-written numbers drift.

## Install

This is a Claude Code / Codex / skills.sh skill (prompt + reference markdown, no runtime dependencies).

```bash
# Claude Code
git clone https://github.com/z8ilon1g/operating-dashboard-skill.git ~/.claude/skills/dashboard-builder

# Codex / skills.sh
npx skills add z8ilon1g/operating-dashboard-skill
```

## What's inside

| Path | Content |
|---|---|
| `SKILL.md` | Entry point: two-stage overview + 11 hard rules |
| `references/01-设计阶段.md` | Design stage in five steps |
| `references/02-落地阶段.md` | Per-screen spec + agent instruction template + batching |
| `references/03-口径纪律.md` | 12 real-world metric-convention failures and how to spot them |
| `references/04-验收清单.md` | Per-screen and overall acceptance checklist |
| `references/05-试跑记录-20261106.md` | Trial run of v1.0 on a new screen |
| `templates/` | Per-screen spec template, data-table field template |
| `examples/` | Full anonymized case: an 8-screen phosphate-mining dashboard |

## Case study

The example comes from a real 8-screen operations dashboard for a phosphate mining company (Nov 2026). The company identity has been anonymized; figures are kept only so the methodology's failure modes remain reproducible.

## License

MIT © 2026 z8ilon1g
