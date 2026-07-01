# Research Layer v2 Reference

This reference explains the method behind `deep-research`. It is not a competing public entry point.

## Method Shape

```text
Gate / Clarify
-> Wide Evidence And Brainstorm
-> Adaptive Grillme
-> Narrowed Evidence Pass
-> PRD Readiness
-> PRD or Downgrade
```

## Why This Shape Exists

Research tasks often fail in three ways:

1. They start too narrow, missing better directions.
2. They ask too few strong questions before producing an artifact.
3. They write a confident PRD from weak evidence.

This method keeps those failure modes visible.

## Phase Responsibilities

| Phase | Responsibility | Must not do |
|---|---|---|
| Gate / Clarify | Decide quick answer vs formal research; identify strong missing questions | Start a full workflow for a lightweight question |
| Wide Evidence | Explore tools, methods, competitors, users, and evidence | Pick the final solution too early |
| Brainstorm | Show 3-5 plausible directions and discarded options | Hide the possibility space |
| Grillme | Resolve readiness-affecting uncertainties | Ask a fixed questionnaire |
| Narrowed Evidence | Check the chosen direction against evidence | Assume Phase 1 evidence still applies after scope changes |
| Readiness | Decide PRD vs downgrade | Pretend unclear ideas are PRDs |

## Strong vs Weak Questions

Strong questions change the artifact. They affect target user, problem, scope, evidence, MVP, acceptance, or delivery format.

Weak questions improve fit. They affect tone, length, formatting, or optional polish.

## Downgrade Principle

A downgrade is not failure. It is the correct artifact for the current clarity level.

Use:

- `idea_note` for blurry ideas
- `discovery_note` for promising but under-evidenced directions
- `decision_brief` for tradeoffs
- `reader_brief` for source understanding

## PRD Principle

A PRD should be earned by clarity and evidence. It should include:

- target user
- problem
- value hypothesis
- MVP
- non-goals
- future roadmap
- acceptance criteria
- risks
- recommendation
- next step

For systems, growth products, or long-term tools, keep the MVP lightweight but preserve the future vision.
