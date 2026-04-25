---
title: Evaluability
type: [concept, metric]
aliases: [verification efficiency, output verifiability, AI output checkability]
tags: []
sources:
  JN: Jakob Nielsen on Substack (2026-03-26) → ../sources/2026-04-25-nielsen-intent-ux.md
last_updated: 2026-04-25
provenance: mostly-sourced
---

# Evaluability

> How rapidly and accurately a user can verify that an AI system's output matches their actual goal. The keystone usability metric of the AI era.

## Definition

【事实】"Evaluability" — also called *verification efficiency* — measures how rapidly and accurately a user can confirm that the AI's output is what they intended. Nielsen positions it as the AI-era replacement for *execution efficiency* (the dominant usability metric of the GUI era). [JN]

## Why it replaces execution efficiency

【事实】In a command-based UI, the user executes each step and inspects the result immediately — execution and verification collapse into one act. In an [[Intent-UX]] flow, the user delegates execution to the AI and then has to *verify* an output they did not produce step-by-step. The bottleneck shifts from "how fast can you do the thing" to "how fast can you confirm the thing was done correctly." [JN]

## Position in the redefined metrics

【事实】[JN]

| Old (command-based) | New (intent-based) |
|---|---|
| Execution Efficiency | **Verification Efficiency (Evaluability)** |

## Why it is hard

【推断】Evaluability fights three structural disadvantages relative to execution efficiency:

1. **Output opacity** — the user did not see the intermediate steps, so they have no scaffolding for evaluating the result.
2. **Authority bias** (the [[Intent-UX]] *Plausibility Trap*) — clean-looking AI outputs trigger trust before scrutiny, suppressing verification.
3. **Asymmetric error visibility** — confident hallucinations and silent omissions are exactly the kinds of errors hardest to catch by inspection alone.

These are not bugs of evaluation; they are why evaluation needs UX support — provenance highlighting, [[Epistemic-UI]] uncertainty maps, conceptual breadcrumbs (see [[Slow-AI]]), execution transparency on the Orchestration Surface.

## Practical implications

【推断】For any AI product, the design question "is this output correct?" is no longer something the *user* answers unaided — it is something the *interface* helps the user answer. Investing in Evaluability means building the verification scaffolding (provenance trails, diffable plans, confidence overlays, side-by-side baseline comparisons) into the product itself, not assuming the user can or will do this work.

---

## Related

- [[Intent-UX]] — the parent paradigm where Evaluability replaces execution efficiency as the load-bearing metric
- [[Epistemic-UI]] — the interface technique that makes Evaluability tractable by surfacing uncertainty
- [[Articulation-Barrier]] — the upstream failure (intent capture); Evaluability is the downstream failure (output verification)
