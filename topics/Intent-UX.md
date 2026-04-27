---
title: Intent UX
type: [paradigm, framework]
aliases: [Intent-Based UX, Intent by Discovery, intent-based outcome specification, AI UX paradigm, supervisory UX]
tags: []
sources:
  JN: Jakob Nielsen on Substack (2026-03-26) → ../sources/2026-04-25-nielsen-intent-ux.md
last_updated: 2026-04-25
provenance: mostly-sourced
---

# Intent UX

> Jakob Nielsen's framing of AI-era interaction design: the user shifts from operator to supervisor, and interaction shifts from issuing commands to specifying outcomes.

## Core thesis

【事实】AI changes computing from command-based interaction ("how?") to **intent-based outcome specification** ("what?") — the user states the result to be achieved and supervises execution rather than executing each step. Nielsen calls this "the first major shift in 60 years" of UI paradigms — a bigger break than the move from typed commands to GUI clicks. [JN]

## Three Eras of UX Goals

【事实】[JN]

| Era | Period | Primary goal | Focus |
|---|---|---|---|
| 1: Business computing | 1960–1995 | Productivity | Faster learning, fewer errors |
| 2: Internet | 1995–2025 | Influence | Persuade buying/engagement via cognitive biases |
| 3: AI | 2026+ | Augmentation | Expand what humans can do and be |

## Intent-based outcome specification

【事实】A usable intent has three components: (1) a desired outcome, (2) constraints bounding acceptable behavior, (3) a delegation boundary defining what the system may execute on the user's behalf. "Plan my Chicago trip" is underspecified until the AI knows the budget, immovable meetings, and whether it can purchase tickets. [JN]

## Supervisory control

【事实】The user shifts from executing tasks directly to supervising AI execution — different failure modes and safeguards than direct manipulation. Analogous to managing a chauffeur, not driving a car. [JN]

## Triple-Layered Design Model

【事实】[JN]

| Layer | Role | Key responsibilities |
|---|---|---|
| 1. Intent Surface | Capture what the user wants | Multimodal input (voice, text, camera); implicit intent inference; ambient context synthesis (calendar, screen, routines) |
| 2. Orchestration Surface | Negotiate before execution | Reveal proposed plan, data provenance, permission choreography; show what changed post-execution; handle multi-stakeholder collaborative intent |
| 3. Direct-Manipulation Surface | GUI fallback for edge-case editing | Users manipulate **plans**, not raw controls (drag tasks, scrub timelines) — direct manipulation migrates one level higher in the abstraction stack |

【推断】The Orchestration Surface is the load-bearing innovation here. Layers 1 and 3 have analogues in pre-AI UX (multimodal input, GUI editing). The Orchestration Surface — making the AI's plan, sources, and permission scope legible *before* execution — is the surface where supervisory control actually happens, and the surface that doesn't exist in command-era UX.

## Redefined usability metrics

【事实】[JN]

| Old (command-based) | New (intent-based) |
|---|---|
| Discoverability | Intent Capture accuracy |
| Error Prevention | Clarification Quality |
| Time to Learn | Ease of Delegation |
| Execution Efficiency | Verification Efficiency ([[Evaluability]]) |
| System Status Visibility | Execution Transparency |
| User Satisfaction | Trust Calibration |

The keystone shift is from execution efficiency to **[[Evaluability]]** — how rapidly and accurately a user can verify that the AI's output matches their actual goal.

## Trust and friction principles

### Intentional Cognitive Friction
【事实】Autonomy is **earned progressively**, not granted all at once. High-stakes actions require deliberate friction: granular authorization, time delays (e.g. 3-second countdowns), provenance highlighting. [JN]

### Plausibility Trap
【事实】Clean, instant AI outputs trigger authority bias — users stop scrutinizing because the result *looks* polished. Intentional friction exists to defeat this. [JN]

### Calibrated Friction Scaling
【事实】Friction is dynamic with user role, organization risk tolerance, and action reversibility. "A $500 transfer requires high friction in personal banking but is frictionless for corporate finance AI." [JN]

### Epistemic UI
【事实】See [[Epistemic-UI]] — interfaces that visually map the system's uncertainty (confidence colors, weak-provenance flags, leap highlights) so cognitive effort goes precisely where judgment is needed. [JN]

## The Articulation Barrier

【事实】See [[Articulation-Barrier]] — roughly half the population in wealthy nations is low-literacy, and writing prose is harder than reading. Text-dependent prompting therefore creates massive usability failure. The Intent Surface fixes this via multimodal capture and implicit inference. [JN]

## Slow AI

【事实】See [[Slow-AI]] — multi-hour AI runs need their own UX vocabulary (run contracts, conceptual breadcrumbs, context reboarding, tiered notifications, salvage value), not generic loading bars. [JN]

## Intent by Discovery — six emerging patterns

【事实】Long-term direction: users shift from *describing* what they want to *exploring* a latent solution space. Creativity becomes discovery, not making. Six patterns: [JN]

| # | Pattern | What it does |
|---|---|---|
| 1 | Spatial Navigation of Latent Space | 2D maps of outputs; dragging the cursor morphs results in real-time (Semantic Topographies); divergent routing |
| 2 | Direct Object Manipulation | User physically alters AI output (e.g. resize image); AI reverse-engineers intent and adjusts supporting elements |
| 3 | Socratic Scaffolding | AI asks diagnostic questions ("Revenue vs. brand awareness?") instead of hallucinating generic outputs |
| 4 | Ephemeral & Generative UIs | Bespoke UI controls spawn dynamically per task and dissolve once intent is locked |
| 5 | Curation as Intent | User dumps PDFs, palettes, voice memos onto a canvas; AI synthesizes conceptual overlaps |
| 6 | Subtractive Sculpting | Start with a maximalist version; user deletes/strikes through unwanted parts (easier than generating from blank) |

## The Cognitive Atrophy Loop

【事实】"Zero-learning" UX — where users never engage with system logic — is a trap. Without engagement, users suffer cognitive offloading and deskilling, "trapped in a Cognitive Atrophy Loop." Good AI UX functions as a **cognitive exoskeleton** (augmentation), not a **cognitive wheelchair** (replacement). [JN]

## Comparisons

【事实】[JN]

| Dimension | GUI era | AI era |
|---|---|---|
| Friction | Removed it from predetermined paths | Expands range of viable paths, opens unimagined possibilities |
| User role | Executes steps directly | Supervises offscreen execution |
| Interaction unit | Commands (click each icon, inspect each result) | Intents (delegate workflow, system infers procedure) |
| Progression | Batch → Command | Command → Intent |

## Action items (Nielsen's practitioner guidance)

【事实】[JN]

1. Measure intent capture accuracy, not click efficiency.
2. Design the Orchestration Surface — that is where trust is built or lost.
3. Choreograph friction deliberately by task stakes.
4. Plan for slow tasks from day one (run contracts, breadcrumbs).
5. Resist the zero-learning trap; keep users cognitively engaged with AI reasoning.

---

## Related

- [[Articulation-Barrier]] — the literacy/prose-writing failure mode the Intent Surface is designed to solve
- [[Evaluability]] — the keystone replacement for execution efficiency in AI-era usability
- [[Epistemic-UI]] — the interface technique for surfacing AI uncertainty to the supervisor
- [[Slow-AI]] — UX patterns for AI runs that take minutes-to-hours
- [[Cat-Wu]] — the team-side mirror; takeaway #6 (95% automation problem) is the Plausibility Trap restated
