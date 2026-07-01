# Deep Research Skill

[中文说明 / Chinese README](README.zh-CN.md)

A lightweight skill bundle for turning vague research requests into clear, evidenced, and usable outputs.

It is designed for agent runtimes that support `SKILL.md` files, but the method can also be copied into any AI assistant instruction system.

## What It Does

`deep-research` is the public entry point for research-like work:

- market and competitor research
- product discovery
- PRD preparation
- paper or literature-oriented discovery
- open-ended decision research
- fuzzy ideas that need to become clear

The core chain is:

```text
Gate / Clarify
-> Visible Brainstorm
-> Adaptive Grillme
-> Narrowed Evidence Pass
-> PRD readiness check
-> PRD or downgrade
```

The important behavior is not "always produce a big report." The important behavior is to choose the right level of output:

- quick answer for lightweight questions
- `idea_note` when the idea is still blurry
- `discovery_note` when the direction exists but evidence is thin
- `decision_brief` for tradeoff decisions
- `reader_brief` for source understanding
- PRD only when readiness is high enough

## What's Included

```text
skills/
  deep-research/SKILL.md
  grillme/SKILL.md
references/
  research-layer-v2.md
  routing-contract.md
  smoke-tests.md
examples/
  market-research.md
  paper-search.md
  product-discovery-to-prd.md
  quick-answer-no-research.md
```

## What Is Not Included

This v0.1 package intentionally excludes heavier local backends:

- GitHub harvesting tools
- web scraping scripts
- academic paper pipeline scripts
- local task memory, caches, or private data
- workspace-specific routing files

Agents can still use ordinary web search, local file reading, or their own installed tools as evidence sources.

## Install

Copy the two skill folders into your agent runtime's skill directory.

For Codex-style skill directories, that usually means:

```text
~/.codex/skills/deep-research/
~/.codex/skills/grillme/
```

Then start a fresh session so the runtime can reload the skill list.

## Recommended Use

Try these prompts in a new session:

- "帮我调研一下 AI 代码工具市场，开源工具和方法论都要看。"
- "我有个想法，想做成 PRD，帮我挖挖：一个给大学生用的 AI 简历成长系统。"
- "找一下 LLM agent memory 这个方向的论文。"
- "简单解释一下 RAG 是什么。"

The first three should route through `deep-research`; the last should be answered directly.

## License

Default recommendation: MIT.

`grillme` is adapted from `Jekudy/grillme-skill`, which is MIT licensed. Keep attribution when redistributing.
