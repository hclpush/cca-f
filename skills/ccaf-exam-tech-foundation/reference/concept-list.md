# CCA-F Foundation Concepts — 38 concepts in 8 categories

The foundational computer-science concepts a non-technical learner needs to read CCA-F exam material fluently. Each is taught only as far as the exam needs it.

Each concept has:
- **CCA-F anchor** — the specific exam domain/topic/scenario where the concept appears.
- **Prerequisite** — what to understand first (— means none; it's an entry point).

Domains: **D1** Agentic Architecture & Orchestration · **D2** Tool Design & MCP Integration · **D3** Claude Code Configuration & Workflows · **D4** Prompt Engineering & Structured Output · **D5** Context Management & Reliability.
Scenarios: Customer Support Resolution Agent · Code Generation with Claude Code · Multi-Agent Research System · Developer Productivity · Claude Code for CI · Structured Data Extraction.

---

## Category 1 — Programming basics

1. **Loop**
   - CCA-F anchor: D1 agent loop — the model acts, observes, repeats until a stop condition.
   - Prerequisite: —

2. **Function**
   - CCA-F anchor: D2 tool design — a tool is fundamentally a function the model can call.
   - Prerequisite: —

3. **Decorator**
   - CCA-F anchor: D2 — the SDK pattern that registers a function as a callable tool.
   - Prerequisite: Function

4. **Class**
   - CCA-F anchor: D2 — SDK objects (clients, tool definitions) are instances of classes.
   - Prerequisite: Function

5. **Variable & data types (string, integer, boolean, null)**
   - CCA-F anchor: D4 structured output — schema fields declare types; a distractor often swaps a number for a string.
   - Prerequisite: —

6. **Conditional (if/else)**
   - CCA-F anchor: D1 — agent routing and when-to-use-a-tool decisions.
   - Prerequisite: Variable & data types

7. **Exception / error handling**
   - CCA-F anchor: D5 reliability — retries, fallbacks, handling a failed tool call gracefully.
   - Prerequisite: Conditional (if/else)

8. **Callback**
   - CCA-F anchor: D1/D2 — passing a function to be invoked later (e.g. tool execution hooks).
   - Prerequisite: Function

---

## Category 2 — Data formats

9. **JSON**
   - CCA-F anchor: D4 structured output; Structured Data Extraction — model responses as JSON objects.
   - Prerequisite: Variable & data types

10. **JSON Schema**
    - CCA-F anchor: D4 output validation; D3 Claude Code `--json-schema` in CI — enforcing the shape of extracted data.
    - Prerequisite: JSON

11. **Enum**
    - CCA-F anchor: D4 — constraining a field to a fixed set of allowed values (e.g. a category label).
    - Prerequisite: JSON Schema

12. **Nullable type**
    - CCA-F anchor: D4 — a field that may be a value or null; common in extraction schemas for missing data.
    - Prerequisite: Variable & data types, JSON Schema

13. **YAML (config files)**
    - CCA-F anchor: D3 — skill/agent/rule frontmatter and config files are written in YAML.
    - Prerequisite: JSON

---

## Category 3 — APIs & networking

14. **REST API**
    - CCA-F anchor: D1/D2 — the Claude API and MCP-exposed services follow REST conventions.
    - Prerequisite: —

15. **HTTP request / response (GET, POST)**
    - CCA-F anchor: D1 — one model turn is a request in, a response out; the unit of an agent step.
    - Prerequisite: REST API

16. **API key / authentication**
    - CCA-F anchor: D2/D3 — Claude API keys; secrets in CI headless runs.
    - Prerequisite: REST API

17. **Endpoint**
    - CCA-F anchor: D2 — the specific URL an API or MCP server exposes for a capability.
    - Prerequisite: REST API

18. **Rate limiting / timeout**
    - CCA-F anchor: D5 reliability — handling 429s, backoff, and slow tool calls.
    - Prerequisite: HTTP request / response

---

## Category 4 — CLI & environment

19. **Terminal / command line**
    - CCA-F anchor: D3 — Claude Code is driven from the terminal via the `claude` command.
    - Prerequisite: —

20. **CLI flag / argument (e.g. `--flag value`)**
    - CCA-F anchor: D3 — `-p` for headless mode, `--json-schema` for structured CI output.
    - Prerequisite: Terminal / command line

21. **Environment variable**
    - CCA-F anchor: D3 — CI/CD headless mode, API keys passed via env vars rather than hardcoded.
    - Prerequisite: Terminal / command line

22. **stdin / stdout**
    - CCA-F anchor: D3 — Claude Code in CI reads a prompt from stdin and prints results to stdout non-interactively.
    - Prerequisite: Terminal / command line

---

## Category 5 — Infrastructure

23. **Docker**
    - CCA-F anchor: D3 — reproducible environments for running Claude Code in CI.
    - Prerequisite: Terminal / command line

24. **Container**
    - CCA-F anchor: D3 — the isolated unit Docker runs; where a CI agent executes.
    - Prerequisite: Docker

25. **Serverless function (e.g. AWS Lambda)**
    - CCA-F anchor: D1/D2 — a common deployment target for tools and agent endpoints.
    - Prerequisite: Function, REST API

26. **CI/CD pipeline**
    - CCA-F anchor: D3 — Claude Code for Continuous Integration; automated runs triggered on commits/PRs.
    - Prerequisite: Container

---

## Category 6 — Software architecture concepts

27. **Synchronous vs asynchronous**
    - CCA-F anchor: D1 — whether the agent waits for a tool result or continues; orchestration timing.
    - Prerequisite: Function

28. **Parallel vs sequential execution**
    - CCA-F anchor: D1 — running multiple sub-agents at once vs in order; Multi-Agent Research System.
    - Prerequisite: Synchronous vs asynchronous

29. **Caching**
    - CCA-F anchor: D5/D4 — prompt caching reuses a stable prefix to cut cost and latency.
    - Prerequisite: Token / tokenization

30. **State / stateless**
    - CCA-F anchor: D1/D5 — each API call is stateless; conversation state must be re-sent each turn.
    - Prerequisite: HTTP request / response

31. **Idempotency**
    - CCA-F anchor: D5 reliability — a retried operation that produces the same result without duplicate side effects.
    - Prerequisite: State / stateless

---

## Category 7 — Dev workflow

32. **Git basics (repo, branch, pull request, commit)**
    - CCA-F anchor: D3 — Code Generation with Claude Code; agents operate on branches and open PRs.
    - Prerequisite: —

33. **Glob pattern (file path matching like `**/*.ts`)**
    - CCA-F anchor: D3 — `.claude/rules/` path-scoped rules use globs in `paths:` frontmatter.
    - Prerequisite: —

34. **Config file / settings file**
    - CCA-F anchor: D3 — settings.json, CLAUDE.md, MCP config that change behavior without code changes.
    - Prerequisite: YAML (config files)

---

## Category 8 — LLM-specific (minimum viable understanding)

35. **Token / tokenization**
    - CCA-F anchor: D5 — context window and cost are measured in tokens.
    - Prerequisite: —

36. **Context window**
    - CCA-F anchor: D5 context management — the finite span of tokens the model can attend to.
    - Prerequisite: Token / tokenization

37. **Prompt / system prompt**
    - CCA-F anchor: D4 — the system prompt sets persistent instructions; prompt engineering is a whole domain.
    - Prerequisite: Token / tokenization

38. **Streaming**
    - CCA-F anchor: D5/D1 — incremental token-by-token responses; affects latency and UX.
    - Prerequisite: Token / tokenization
