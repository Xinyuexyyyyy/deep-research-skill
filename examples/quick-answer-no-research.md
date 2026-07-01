# Example: Quick Answer, No Research

Prompt:

```text
简单解释一下 RAG 是什么。
```

Expected route:

```text
direct answer
```

Expected behavior:

- No `deep-research` stage card.
- No formal evidence workflow.
- No PRD, no brainstorm, no grillme.

Good answer shape:

```text
RAG, or retrieval-augmented generation, means the model first retrieves relevant external information, then uses that information to generate an answer. It is useful when the model needs up-to-date or private knowledge that is not reliably stored in its parameters.
```
