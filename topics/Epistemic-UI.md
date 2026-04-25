---
title: Epistemic UI
type: [concept, design-pattern]
aliases: [uncertainty-aware UI, confidence-surfacing UI, epistemic interface]
tags: []
sources:
  JN: Jakob Nielsen on Substack (2026-03-26) → ../sources/2026-04-25-nielsen-intent-ux.md
last_updated: 2026-04-25
provenance: mostly-sourced
---

# Epistemic UI

> Interfaces that visually map the AI system's own uncertainty, directing the user's cognitive effort precisely to the areas where their judgment is most needed.

## Definition

【事实】An Epistemic UI is one that "visually maps the system's uncertainty." Instead of presenting AI output as uniformly confident text or pixels, it highlights where the system made probabilistic leaps, where its provenance is weak, and how confident it is at each part of the answer (often via colour-coding). [JN]

## What it surfaces

【事实】[JN]

| Surfaced signal | What it tells the user |
|---|---|
| Probabilistic leaps | "This step was inference, not retrieval — scrutinize it." |
| Weak provenance | "This claim has no strong source backing it." |
| Confidence levels | "We are 90% confident here, 30% confident there." |

## Why it matters

【事实】Epistemic UI is the operationalization of [[Evaluability]] on the output surface — it is how the interface helps the supervisor know *where to look*. Without it, the user must verify uniformly across all output, which is expensive and rarely happens; with it, scrutiny is directed where it pays off. [JN]

## Defeats the Plausibility Trap

【事实】The [[Intent-UX]] *Plausibility Trap* describes how clean, instant AI outputs trigger authority bias and turn off scrutiny. Epistemic UI is the structural counter — by visually disrupting the polished surface with confidence and provenance signals, it reintroduces the friction that polished output suppresses. [JN]

## Design implications

【推断】"Add a confidence score" is not the whole pattern. The richer move is differential — show *where* the system is uncertain, not just *that* it is uncertain on average. A single global "78% confident" number invites the user to either accept or reject the whole output; a heatmap or per-claim provenance trail invites them to verify selectively, which is what supervisory control actually requires.

【推断】Risk: Epistemic UI can decay into "uncertainty theatre" — confidence numbers that are themselves poorly calibrated, or provenance highlights that point at sources the user can't actually evaluate. The signal has to be both honest and actionable to do work.

---

## Related

- [[Intent-UX]] — parent paradigm; Epistemic UI is one of its core trust-building techniques
- [[Evaluability]] — the metric Epistemic UI is designed to make tractable
