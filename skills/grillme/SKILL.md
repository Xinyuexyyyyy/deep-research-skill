---
name: grillme
description: Use for deep Socratic interviewing before committing to a complex idea, plan, decision, requirement, workflow, product direction, architecture, retrospective conclusion, or high-rework-risk task. Trigger when the user asks to be grilled, questioned, pressure-tested, or when a task is underspecified and direct execution would likely cause rework. Do not use for simple explicit commands or already-approved next steps.
---

# Grillme

Use Socratic questioning to help the user articulate what they already know but have not made explicit.

Core source: `Jekudy/grillme-skill` (`https://github.com/Jekudy/grillme-skill`, MIT). This version adapts it for agent workflows, Chinese or bilingual conversation, and task-first execution.

In `deep-research`, grillme sits after visible brainstorm and before PRD-level convergence. Its job is to decide whether the research task is clear enough to become a PRD, should continue questioning, or should downgrade.

## Core Rule

Ask one important question at a time. Do not dump a questionnaire.

The goal is not to collect trivia. The goal is to expose assumptions, conflicts, constraints, risks, and acceptance criteria before the work becomes expensive.

Do not cap grillme at a fixed number of rounds. Continue or stop based on whether unresolved questions still affect the next artifact.

## Question Classes

Every question is either strong or weak.

### Strong Questions

A strong question affects whether the next artifact can be correct.

Treat a question as strong if the answer can change:

- The goal.
- The target user or audience.
- The research object or scope.
- The decision standard.
- The evidence/source strategy.
- The delivery format or structure.
- The MVP boundary.
- The acceptance criterion.

Examples:

- "Who is the primary user or reader?"
- "Is this for product planning, investment judgment, writing, or learning?"
- "Which market, population, or use case are we studying?"
- "What result would make this useful enough?"
- "What assumption would make the whole plan wrong?"

Unanswered strong questions affect readiness. If they cannot be reasonably assumed, keep grilling or downgrade the output.

### Weak Questions

A weak question improves fit but does not block progress.

Examples:

- "Do you prefer a formal or conversational tone?"
- "Should the final output use more tables or prose?"
- "Do you have a citation style preference?"
- "How long should the final memo be?"
- "Should we include an executive summary?"

Weak questions can be skipped. If skipped, record the default assumption and continue.

## When To Stop

Stop grilling when one of these is true:

- The next executable step is clear.
- The main decision has an explicit owner and acceptance criterion.
- No unresolved strong question remains.
- Remaining strong questions can be handled with explicit assumptions.
- Further questions are no longer changing the plan.
- Continuing to ask would cost more attention than it saves rework.
- The user asks to stop, pause, or move to execution.

Continue grilling when one of these is true:

- A strong question is still unanswered.
- Not answering would likely change the goal, scope, evidence, boundary, or acceptance.
- The current information cannot determine which internal capability or workflow to call.
- The user's latest answer introduces a new key uncertainty.

## Question Waves

### Wave 1: Surface

Ask about goal, context, constraints, and desired outcome. Prioritize strong questions.

Examples:

- "What result matters most here: speed, quality, control, or future reuse? I would prioritize control because this affects later handoff. Do you agree?"
- "What is explicitly out of scope for this round?"

### Wave 2: Friction

Ask about edge cases, conflicts, hidden dependencies, and tradeoffs. Continue only while the answers can change the plan.

Examples:

- "If we can preserve only one thing, should we preserve delivery speed or method clarity?"
- "Where would this become painful for you to use without an assistant?"

### Wave 3: Blind Spots

Ask about contradictions, assumptions, and failure modes. Stop when only weak preference questions remain.

Examples:

- "What assumption would make this whole plan wrong?"
- "What would make you say later: this technically worked, but I still cannot use it?"

## Between Waves

After each wave, summarize briefly:

- **Understood:** 2-4 facts or decisions.
- **Strong gaps:** important unanswered questions that affect readiness.
- **Weak gaps:** optional preferences or polish questions.
- **Risk:** one concrete risk if execution starts now.
- **Next question:** one question, with your recommended answer when useful.

## How To Ask

- Ask in the user's language unless they request otherwise.
- Prefer "what makes this true?" over blunt "why?"
- If you ask a choice question, include your recommendation and reason.
- Do not ask more than one question per user turn.
- Do not mix weak questions into a strong-question turn unless it reduces user burden.
- Do not turn small clear tasks into a workshop.
- If the user says "you decide" on a weak question, make a default assumption and continue.
- If the user says "you decide" on a strong question, either state the assumption and risk or explain why this one must be answered.

## Output At Close

When the grill is done, produce a compact handoff:

```text
Goal:
Non-goals:
Key decisions:
Strong unanswered questions:
Weak unanswered questions:
Risks:
Acceptance:
Readiness: Ready / Partially ready / Not ready
Next step:
Where to record:
```

If the result becomes a project task, record the handoff in the task's planning or state document.
