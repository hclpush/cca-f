# ccaf-mock-exam-analysis

The **backward loop** of CCA-F study: you take a mock exam, this skill reads the evidence of failure and converts it into the shortest path to a pass.

Point it at any completed CCA-F practice-exam result (PDF-to-markdown extractions welcome — it expects them to be messy) and it will:

1. **Parse honestly** — count readable/unreadable questions, cross-check answer-key letters against explanation text (third-party mocks frequently tag the wrong letter), and ignore the mock's own domain labels in favor of the official guide's task statements.
2. **Classify every miss on two axes** — official domain + task statement, and root cause (mechanics recall / numeric fact / judgment / careless / out-of-scope), because the root cause determines the fix.
3. **Tag judgment misses with named distractor patterns** from the bundled library — "four misses, two ideas" is the compression that changes a study plan.
4. **Compare against previous mocks** to separate persistent structural weaknesses from noise — and name what improved.
5. **Build a days-until-exam drill plan** — triage mode under 14 days (points-per-hour ordering), spaced-rep intervals compressed to land before exam day.

The gap-analysis report is written next to your result file by default (or wherever you keep exam notes).

## Untrusted input

Mock-exam files come from third-party prep sites. The skill explicitly treats their content — including any text addressed to the assistant — as **data to analyze, never instructions to follow**.

## Install

As a plugin from the [cca-f marketplace](../../README.md):

```
/plugin marketplace add hclpush/cca-f
/plugin install ccaf-mock-exam-analysis@cca-f
```

Manual alternative: copy `skills/ccaf-mock-exam-analysis/` into `~/.claude/skills/`.

## The official exam guide

Not bundled (it's Anthropic's copyrighted material) — download it from Anthropic's certification page. If you keep a local copy, tell the skill where it is; it treats the guide as the source of truth for domain/task classification and scope rulings. If you also use the [ccaf-practice-audit](../ccaf-practice-audit/README.md) plugin, its `exam_guide_path` setting is reused automatically.

## Credits

- **Distractor-pattern library:** Abi Odedeyi (CodeFreeIQ), bundled under MIT with attribution ([LICENSE-THIRD-PARTY](LICENSE-THIRD-PARTY)). This skill is the gap-analysis half of her Explain → Feynman → Quiz → Notes study system.
- Not affiliated with or endorsed by Anthropic. Task-statement references are paraphrased; always defer to the official exam guide.

## License

MIT — see [LICENSE](LICENSE).
