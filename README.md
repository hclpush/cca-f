# cca-f

Skills for preparing for the Anthropic **Claude Certified Architect – Foundations (CCA-F)** exam.

> **Disclaimer — unofficial.** These are community study aids. They are **not affiliated with, endorsed by, or produced by Anthropic**. "CCA-F," "Claude Certified Architect," and "Claude" are referenced for study purposes only. Anthropic's official exam guide is the source of truth.

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

## Source of truth

Concept anchors, exam domains, weights, and scenario names are grounded in the **official Anthropic CCA-F Certification Exam Guide** (v0.1). This repo does **not** redistribute that guide — download the current version from Anthropic's certification page.

Direct PDF link at time of writing (may rotate — prefer the certification page):
<https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1773274827%2FClaude+Certified+Architect+%E2%80%93+Foundations+Certification+Exam+Guide.pdf>

Claude-specific facts (CLI flags, config paths) are cross-checked against <https://docs.claude.com>.

## Contributing

The exam and Claude Code both change. Before editing any concept anchor:

- **Verify Claude-specific claims** (CLI flags, config-file paths, MCP behavior) against docs.claude.com — never assert them from memory.
- **Verify exam structure** (domains, weights, scenarios, in/out-of-scope topics) against the *current* official exam guide, not third-party prep sites.
- **Note the source and date** of any change so the next contributor knows what was checked.

Two concepts — **Caching** and **Streaming** — are anchored to topics the guide lists as *out of scope*. They're kept intentionally as background (teach the concept, flag "not tested"). Don't remove them as errors.
