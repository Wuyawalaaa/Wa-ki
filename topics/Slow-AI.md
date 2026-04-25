---
title: Slow AI
type: [concept, design-pattern]
aliases: [long-running AI UX, multi-hour AI tasks, async AI UX, extended-duration AI]
tags: []
sources:
  JN: Jakob Nielsen on Substack (2026-03-26) → ../sources/2026-04-25-nielsen-intent-ux.md
last_updated: 2026-04-25
provenance: mostly-sourced
---

# Slow AI

> AI tasks that run for minutes to hours instead of seconds. Their UX requirements are categorically different from real-time AI, and generic loading bars are not the answer.

## The phenomenon

【事实】As AI systems take on longer-horizon tasks (research, multi-step agentic workflows, codebase-wide refactors, batch generation), the user can no longer sit and watch — but also can't be fully absent. Nielsen calls this regime **Slow AI** and argues it needs its own UX vocabulary. [JN]

## Five UX interventions

【事实】[JN]

| # | Intervention | What it does |
|---|---|---|
| 1 | **Clarification & Run Contracts** | Upfront questions resolve ambiguity before work starts; an explicit contract defines time window, cost cap, and "done" criteria |
| 2 | **Conceptual Breadcrumbs** | Synthesized summaries of intermediate conclusions — meaningful progress, not raw log spam |
| 3 | **Context Reboarding** | When the user returns, a resumption summary reminds them of the original intent and the key decisions made so far |
| 4 | **Tiered Notifications** | Push only for critical blocks; email for quality decisions; batched digests for the rest. Respects the user's attention budget |
| 5 | **Progressive Disclosure & Salvage Value** | Show partial results early; explicitly display reusable artifacts if the user stops the run partway |

## Why generic progress bars fail

【推断】A loading bar communicates "the system is working." A Slow AI run needs to communicate three additional things: *what* it is working on, *how* its choices are tracking against the user's intent, and *what is recoverable* if the run is interrupted. These are content-shaped signals, not duration-shaped — which is why the five interventions above are about meaning (contracts, conceptual summaries, salvage artifacts) rather than time (percent-complete bars).

## Design implication: salvage-first

【推断】The salvage-value pattern (#5) is the most underrated of the five. Most product teams treat "user cancelled the run" as an error state; treating partial output as a first-class deliverable changes the risk profile of letting users start long runs at all. If stopping at 40% still produces something useful, users will be willing to start runs that stopping at 0% would have made unthinkable.

## Relationship to the parent paradigm

【事实】Slow AI extends [[Intent-UX]] across time. The same Triple-Layered Model applies — Intent Surface (run contract), Orchestration Surface (breadcrumbs, transparency, tiered notifications), Direct-Manipulation Surface (mid-run plan editing) — but stretched over a duration that breaks the user's attention. Run contracts and reboarding are the techniques for spanning that gap. [JN]

---

## Related

- [[Intent-UX]] — parent paradigm; Slow AI is its time-extended form
- [[Evaluability]] — verification cost grows with task duration; conceptual breadcrumbs exist to keep evaluability tractable
- [[Epistemic-UI]] — uncertainty surfacing is even more important when the user wasn't watching the run
