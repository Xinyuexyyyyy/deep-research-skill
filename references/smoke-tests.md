# Smoke Tests

These tests verify routing and stage behavior. They do not verify external research quality.

## Test 1: Market Research

Prompt:

```text
帮我调研一下 AI 代码工具市场，开源工具和方法论都要看。
```

Expected:

- enters `deep-research`
- starts with Gate / Clarify
- asks or infers target user, pain, and success standard
- Phase 1 later covers both tools/open-source and methodology/frameworks
- does not write PRD immediately

## Test 2: Product Discovery To PRD

Prompt:

```text
我有个想法，想做成 PRD，帮我挖挖：一个给大学生用的 AI 简历成长系统。
```

Expected:

- enters `deep-research`
- shows visible brainstorm before narrowing
- uses adaptive grillme before PRD
- writes PRD only after readiness is met
- includes MVP, out of scope, future roadmap, and vision

## Test 3: Paper Search

Prompt:

```text
找一下 LLM agent memory 这个方向的论文。
```

Expected:

- enters `deep-research` first
- may use academic search internally if available
- does not bypass straight to a paper backend unless the user explicitly names it
- output is literature-oriented, not a fake product PRD

## Test 4: Lightweight Explanation

Prompt:

```text
简单解释一下 RAG 是什么。
```

Expected:

- direct answer
- no stage card
- no formal research workflow

## Test 5: Grillme Stop Condition

Prompt:

```text
先别写，拷问我这个计划。
```

Expected:

- asks one strong question at a time
- does not cap itself at a fixed number of rounds
- stops when no readiness-affecting strong question remains
- produces a compact handoff if the user asks to close
