# cca-f

Skills for preparing for the Anthropic **Claude Certified Architect – Foundations (CCA-F)** exam.

## Skills

### `ccaf-exam-tech-foundation`
Teaches the ~38 foundational computer-science concepts a non-technical learner needs to read CCA-F exam material fluently — JSON, JSON Schema, glob patterns, environment variables, caching, Docker, tokens, and more. Each concept is anchored to the specific exam topic where it appears, and taught only as far as the exam needs it.

It runs a 3-step loop per concept:

1. **Explain** — plain-language definition + real-world analogy + one sentence on why it appears in the CCA-F exam.
2. **Feynman** — one open-recall question.
3. **Quiz** — one MCQ wrapped in a CCA-F-style scenario (never an abstract textbook example).

This is a **prerequisite layer** beneath the `cca-f-exam-prep` skill — meant to unblock a single concept in the moment, then hand the learner back to exam prep. No spaced-rep logging, no distractor-pattern tagging (those belong to `cca-f-exam-prep`).

```
skills/ccaf-exam-tech-foundation/
├── SKILL.md
└── reference/
    ├── concept-list.md   # 38 concepts × 8 categories; CCA-F anchor + prerequisite each
    └── study-method.md   # the 3-step Explain → Feynman → Quiz loop
```

## Install

Copy a skill folder into your Claude Code skills directory:

```bash
cp -R skills/ccaf-exam-tech-foundation ~/.claude/skills/
```
