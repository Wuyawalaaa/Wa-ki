---
title: Jakob Nielsen — Intent by Discovery: Designing the AI User Experience
type: source
source_url: https://jakobnielsenphd.substack.com/p/intent-ux
source_platform: Substack (Jakob Nielsen on UX)
author: Jakob Nielsen, Ph.D.
published: 2026-03-26
fetched: 2026-04-25
---

# Jakob Nielsen — Intent by Discovery: Designing the AI User Experience

**Original URL:** https://jakobnielsenphd.substack.com/p/intent-ux
**Author:** Jakob Nielsen, Ph.D.
**Published:** 2026-03-26
**Fetched:** 2026-04-25

## Core thesis

AI shifts the user's role from **operator to supervisor**, requiring an entirely new UX paradigm beyond chat interfaces. Interaction moves from command-based ("how?") to **intent-based outcome specification** ("what?"). Nielsen frames this as "an entirely new UI paradigm, and the first major shift in 60 years."

> "AI changes computing from command-based interaction to intent-based outcome specification: the user states the result to be achieved."

> "The shift from typing commands to clicking them was much smaller than the AI-driven change in interaction design."

## Three Eras of UX Goals

| Era | Period | Goal | Focus |
|-----|--------|------|-------|
| 1: Business Computing | 1960–1995 | Productivity | Faster learning, fewer errors |
| 2: Internet | 1995–2025 | Influence | Persuade buying/engagement via cognitive biases |
| 3: AI | 2026+ | Augmentation | "Expand what humans can do and be" |

## Intent-Based Outcome Specification

A usable intent has three parts:

1. **Desired outcome**
2. **Constraints** bounding acceptable behavior
3. **Delegation boundary** — what the system may execute on the user's behalf

Example: "Plan my Chicago trip" is underspecified unless the AI knows the budget, immovable meetings, and whether it can purchase tickets.

## Supervisory Control

User shifts from executing tasks directly to supervising AI execution. Different failure modes and safeguards than direct manipulation. Analogous to managing a chauffeur, not driving a car.

## The Articulation Barrier

- Roughly 50% of populations in wealthy nations are low-literacy users.
- Writing descriptive prose is cognitively harder than reading it.
- Text-dependent prompting therefore creates a massive usability failure.
- Fix: multimodal capture (voice, camera, ambient context — calendar, screen content, routines) plus implicit intent inference.

## Triple-Layered Design Model

### Layer 1: Intent Surface
- Accepts multimodal inputs (voice, text, camera).
- Overcomes the articulation barrier via implicit intent inference.
- Synthesizes ambient context.

### Layer 2: Orchestration Surface
- Critical negotiation layer before execution.
- Reveals proposed plan, data provenance, permission choreography.
- Shows what changed post-execution via execution transparency.
- Handles collaborative intent in multi-stakeholder environments.

### Layer 3: Direct-Manipulation Surface
- Traditional GUI as fallback for edge-case editing.
- Users manipulate plans (not raw controls): dragging tasks, scrubbing timelines.
- Direct manipulation migrates "one level higher in the abstraction stack."

## Redefined Usability Metrics

| Old (command-based) | New (intent-based) |
|---|---|
| Discoverability | Intent Capture accuracy |
| Error Prevention | Clarification Quality |
| Time to Learn | Ease of Delegation |
| Execution Efficiency | Verification Efficiency (**Evaluability**) |
| System Status Visibility | Execution Transparency |
| User Satisfaction | Trust Calibration |

**Evaluability:** "how rapidly and accurately a user can verify that the AI's output matches their actual goal."

## Critical Design Principles

### Intentional Cognitive Friction
- Autonomy is **earned progressively**, not granted all at once.
- High-stakes actions require friction: granular authorization, time delays (3-second countdowns), provenance highlighting.
- Combats the **Plausibility Trap** — clean, instant interfaces trigger authority bias and turn off scrutiny.

### Epistemic UI
Interfaces that "visually map the system's uncertainty" and highlight:
- Probabilistic leaps
- Weak provenance data
- Confidence levels (color-coded)

Directs cognitive effort precisely to areas requiring judgment.

### Calibrated Friction Scaling
Dynamic friction based on user role, organization risk tolerance, and action reversibility.

> "A $500 transfer requires high friction in personal banking but is frictionless for corporate finance AI."

## Slow AI: Extended-Duration Tasks

Five UX interventions for multi-hour AI runs:

1. **Clarification & Run Contracts** — Upfront questions; explicit contracts showing time window, cost cap, "done" definition.
2. **Conceptual Breadcrumbs** — Synthesized summaries of intermediate conclusions (not generic logs).
3. **Context Reboarding** — Resumption summaries reminding users of original intent and key decisions.
4. **Tiered Notifications** — Immediate push only for critical blocks; low-priority emails for quality decisions; batched digests.
5. **Progressive Disclosure & Salvage Value** — Show partial results early; explicitly display reusable artifacts if user stops the run.

## Intent by Discovery (long-term vision)

Shift from describing (current) toward exploring latent solution spaces. Creativity becomes discovery, not making.

### Six Emerging UX Patterns

1. **Spatial Navigation of Latent Space** — 2D maps of outputs; dragging cursor morphs results in real-time ("Semantic Topographies"); divergent routing.
2. **Direct Object Manipulation** — User physically alters AI output (resize image); AI reverse-engineers intent and adjusts supporting elements.
3. **Socratic Scaffolding** — AI asks diagnostic questions ("Revenue vs. brand awareness?") instead of hallucinating generic outputs.
4. **Ephemeral & Generative UIs** — Bespoke UI controls spawn dynamically based on exploration context; dissolve once intent is locked.
5. **Curation as Intent** — Multimodal input: dump PDFs, color palettes, voice memos onto canvas; AI synthesizes conceptual overlaps.
6. **Subtractive Sculpting** — Start with maximalist version; user deletes/strikes through unwanted parts (easier than generating from blank).

## Key Comparisons

**AI UX vs. GUI Era:**
- GUI removed friction in predetermined paths.
- AI expands the range of viable paths, opens unimagined possibilities.
- GUI: user executed steps directly. AI: user supervises offscreen execution.

**Command-Based vs. Intent-Based:**
- Command: "strike every blow" (click each icon) with immediate inspection.
- Intent: delegate workflow; system infers procedure.

**Batch → Command → Intent progression:**
- Batch: submit entire workflow at once.
- Command: alternating human-computer turns.
- Intent: AI infers and executes autonomously.

## The Cognitive Atrophy Loop

> "If users never need to learn how a system works... they suffer cognitive offloading and deskilling... trapped in a Cognitive Atrophy Loop."

Good AI UX functions as a **cognitive exoskeleton** (augmentation), not a **cognitive wheelchair** (replacement).

## Action items (Nielsen's practitioner guidance)

1. Measure intent capture accuracy, not click efficiency.
2. Design the orchestration layer (where trust is built/lost).
3. Choreograph friction deliberately by task stakes.
4. Plan for slow tasks from day one (run contracts, breadcrumbs).
5. Resist the zero-learning trap; keep users cognitively engaged with AI reasoning.
