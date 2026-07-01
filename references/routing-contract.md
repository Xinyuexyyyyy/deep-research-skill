# Routing Contract

This package uses one public research entry point: `deep-research`.

## Default Routing

Route to `deep-research` for substantial requests involving:

- research
- market or competitor analysis
- paper or literature discovery
- product discovery
- PRD preparation
- MVP definition
- user pain exploration
- decision research
- fuzzy ideas that need investigation

## Lightweight Exception

Do not route to `deep-research` for:

- simple definitions
- quick facts
- lightweight explanations
- casual chat
- already-approved execution tasks

Example:

```text
User: 简单解释一下 RAG 是什么。
Expected: direct answer, no formal stage card.
```

## Explicit Backend Exception

If the user explicitly names a backend skill or tool, the agent may use it directly.

Examples:

```text
User: 直接用 paper-discovery 搜这些关键词。
Expected: use the named backend.

User: 调用 academic-deep-research 做系统综述。
Expected: use the named backend if installed.
```

If the user simply says "find papers" or "do a literature review," route through `deep-research` first.

## Recommended Public Behavior

Before starting formal research, the agent should show:

```text
Current stage: Gate / Clarify
Goal: decide whether this needs formal research and clarify the strongest missing variables.
Done when: target user, problem, and success standard are clear enough, or assumptions are stated.
```

Then ask at most one strong question unless the user has already provided enough context.

## Internal Backends

Backends can include search tools, source readers, GitHub discovery, academic paper tools, or research templates.

They are implementation details. Their outputs should be synthesized back into `deep-research`, not handed to the user raw.
