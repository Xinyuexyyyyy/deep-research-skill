# Example: Paper Search

Prompt:

```text
找一下 LLM agent memory 这个方向的论文。
```

Expected route:

```text
deep-research
-> Gate / Clarify
-> academic evidence search internally if available
-> literature-oriented synthesis
```

Expected behavior:

- Start from `deep-research`, not a backend paper tool, unless the user explicitly names that tool.
- Clarify whether the user needs a quick reading list, systematic review, SOTA map, research gap scan, or citations for writing.
- Do not force a product PRD.
- If evidence is thin, deliver a `discovery_note` or literature brief.

Good first answer shape:

```text
Current stage: Gate / Clarify
Goal: decide the depth and use of this paper search.
Done when: I know whether you need a quick list, a SOTA map, or a review-ready evidence table.

One strong question: is this for choosing a research direction, writing related work, or just building an initial reading list?
```
