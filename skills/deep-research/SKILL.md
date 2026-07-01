---
name: deep-research
description: Use as the public entry point for substantial research requests, including market research, competitor research, paper or literature discovery, product discovery, PRD preparation, MVP definition, user pain exploration, decision research, and fuzzy ideas that need investigation. Do not use for lightweight definitions, simple facts, or explicit non-research execution tasks.
---

# Deep Research

`deep-research` is the single public entry point for research-like work.

It turns a vague idea, research question, academic/paper request, competitor/market question, or product direction into an executable, evidenced, and appropriately scoped output.

It may use other tools, search, files, or optional sub-skills internally, but those are not default public entry points. This layer owns the user-facing flow, synthesis, readiness checks, and final artifact choice.

## Core Chain

```text
Gate / Clarify
-> Visible Brainstorm
-> Adaptive Grillme
-> Narrowed Evidence Pass
-> PRD readiness check
-> PRD or downgrade
```

## When To Use

Use this skill when the user asks for:

- research, deep research, investigation, or discovery
- market or competitor research
- paper search, literature review, SOTA, or research gaps
- product discovery, PRD, MVP, user pain, or assumptions
- open-ended strategic or product decisions
- a fuzzy idea that needs to be made clear

## When Not To Use

Do not enter formal deep research when:

- The user asks for a short definition, concept explanation, or single fact.
- The user is already executing a concrete non-research task, such as editing code or formatting a document.
- The user is casually brainstorming and does not want a formal research flow.
- The user explicitly names a non-research skill or tool.
- A quick answer can satisfy the request.

If unsure whether the request is lightweight, answer lightly first and offer to go deeper.

## Stage Cards

At the start of each formal stage, show a short stage card:

```text
Current stage: <stage name>
Goal: <what this stage resolves>
Done when: <what proves this stage is complete>
```

Keep the card short. The stage card should orient the user, not become a report.

## Phase 0: Gate / Clarify

First decide whether the user wants a quick answer or formal research.

Before formal research, clarify the strongest missing questions. Default strong questions:

1. **Who is this for?** The target user, reader, customer, or decision owner.
2. **What pain or decision matters?** What goes wrong if this is not solved?
3. **What counts as success?** How will the user judge the result?

These are default strong questions, not a fixed interview script. Do not repeat questions already answered in context.

If the user does not answer, state an explicit assumption and mark it as unconfirmed.

If the user says "look around first," enter Phase 1 with unconfirmed direction.

If the missing information would make the work obviously wrong, stop and ask one strong question.

Recommended internal note:

```text
Assumptions:
- ...
Unknowns:
- ...
```

## Phase 1: Wide Evidence And Visible Brainstorm

Goal: see enough possibility space before narrowing.

Do:

1. Scan at least three relevant evidence lanes.
2. Record sources, findings, and confidence for yourself.
3. Produce 3-5 possible directions.
4. For each direction, include one-line value, main upside, and main downside.
5. Name obvious discarded directions and why they are not worth pursuing now.

### Evidence Lanes

Default lanes:

| Lane | What it answers | Typical sources |
|---|---|---|
| Tools / open source | What can be used, adapted, or avoided | GitHub, product docs, demos, examples |
| Methodology / frameworks | Mature ways to solve or judge the problem | guides, expert posts, papers, handbooks |
| Competitors / products | How existing products package, price, and differentiate | websites, pricing pages, reviews, case studies |
| User / community pain | What real users complain about or work around | forums, Reddit, HN, communities, interviews |
| Academic / data | What research evidence, metrics, or theory exist | papers, reports, datasets, white papers |

If the user asks for both tools/projects and methodology/frameworks, cover both. Do not replace one with the other.

### Visible Phase 1 Output

Show the user a compact brainstorm:

```text
I found these possible directions:
- Direction A: ... Upside: ... Downside: ...
- Direction B: ... Upside: ... Downside: ...
- Direction C: ... Upside: ... Downside: ...

Reusable tools/projects:
- ...

Reusable methods/frameworks:
- ...

Discard for now:
- ...

Which direction should we narrow into? My recommendation is ... because ...
```

Do not write a PRD in Phase 1.

Stop Phase 1 when the user chooses a direction, asks for another brainstorm, or there are no useful new directions.

## Phase 2: Adaptive Grillme

Goal: expose uncertainties that would make the next artifact wrong.

Use `grillme` behavior here: ask one important question at a time, prioritizing strong questions over weak questions.

Strong questions can change:

- goal
- target user
- scope
- evidence strategy
- decision standard
- delivery format
- MVP boundary
- acceptance criteria

Weak questions only improve style, formatting, or preference.

Do not cap grillme at 1-3 rounds. Continue while unresolved strong questions still affect readiness. Stop when the remaining gaps can be handled as assumptions, the user accepts the risk, or further questioning no longer changes the plan.

Close with a compact handoff:

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
```

## Phase 3: Narrowed Evidence Pass

Goal: make sure the chosen direction is actually supported.

After grillme narrows the direction, do one of two things:

1. Run a small second-pass evidence check focused on the chosen direction.
2. If no new search is needed, explicitly map Phase 1 evidence to the current decisions.

Use this mapping before PRD:

| Confirmed decision | Supporting evidence | Evidence strength | Gap / next validation |
|---|---|---|---|
| ... | ... | High / Medium / Low / Unverified | ... |

If evidence does not support the narrowed direction, do not write a PRD. Continue evidence work or downgrade to `discovery_note` / `decision_brief`.

Then define three lists with the user:

- **MVP:** what the first version must do.
- **Future:** meaningful later work.
- **Out of scope:** what this effort will not do.

If there are multiple viable options, compare them with tradeoffs and give a recommendation.

Stop Phase 3 only when the MVP boundary is clear enough or the output is downgraded.

## Phase 4: PRD Readiness / Downgrade / Write

Only write a PRD when readiness is sufficient.

### PRD Readiness

Before writing a PRD, check:

- Target user is clear.
- User problem or decision is clear.
- Non-goals are clear.
- MVP wedge is clear.
- At least three key assumptions are listed.
- Each key assumption has evidence or a validation action.
- Narrowed Evidence Pass is complete.
- Strong grillme questions are answered or accepted as unresolved risk.
- Acceptance criteria are measurable.
- Evidence strength is labeled.

### Downgrade Outputs

If readiness is not sufficient, downgrade instead of pretending the work is PRD-ready:

- `idea_note`: the idea is still too blurry.
- `discovery_note`: direction exists, but evidence or assumptions are not strong enough.
- `decision_brief`: the user needs a tradeoff memo, not product specs.
- `reader_brief`: the task is source understanding, not product definition.

When downgrading, tell the user what can be delivered now, what is assumed, and what would upgrade it to a PRD.

### PRD Template

```markdown
# <Product / Feature Name> PRD

## 1. Overview
One sentence describing what this is.

## 2. Target User
- Primary user:
- User pain:
- What happens if unsolved:

## 3. Value Hypothesis
We believe [feature] helps [user] solve [pain], creating [value].

## 4. MVP Scope
The first version must include:
1. ...
2. ...

## 5. Out of Scope
1. ...

## 6. Future
### V1 / V2 Roadmap
1. ...

### Vision / North Star
If this system works long-term, what capability does it become?

## 7. Acceptance Criteria
- What proves it works?
- How does the user verify it?

## 8. Key Risks
- Verified:
- Unverified:
- Not currently verifiable:

## 9. Recommendation
- Recommended direction:
- Why not the alternatives:

## 10. Next Step
- What task follows:
- What must the user confirm:
```

If the user asks for a system, growth direction, platform, or long-term capability, do not let a lightweight MVP erase future imagination. Keep MVP small, but include roadmap and North Star.

## Evidence Notes

Keep evidence structured and traceable. Use a table, CSV, or notes with:

- source
- key finding
- confidence
- relevance to decision

Do not dump raw evidence into the user-facing answer unless the user asks for it.

## Optional Internal Capabilities

Depending on the runtime, `deep-research` may use other tools or skills internally:

- source/material intake for URLs, PDFs, or pasted material
- GitHub or open-source project search
- web search and page reading
- academic paper search or screening
- competitor research templates
- product discovery templates

These are optional backends. They should not replace `deep-research` as the public entry point unless the user explicitly asks for a specific backend.

## Safety Rules

1. Do not force every research request into a PRD.
2. Do not skip visible brainstorm before narrowing.
3. Do not skip grillme when strong questions remain.
4. Do not write a PRD before narrowed evidence is checked or mapped.
5. Do not expose internal raw evidence by default.
6. Do not over-route lightweight questions. Answer simply when simple is enough.
7. State confidence: confirmed, high, medium, low, or unverified.
