---
title: marketingskills
type: [tool, instance]
aliases: [marketingskills, Corey Haines marketingskills, marketing skills toolkit]
tags: []
sources:
  CH: marketingskills toolkit via Xiaohongshu (2026-04-25) → ../sources/2026-04-25-marketingskills-corey-haines.md
last_updated: 2026-04-25
provenance: mostly-sourced
---

# marketingskills

> An MIT-licensed library of 25 marketing-specific AI skills by Corey Haines (Conversion Factory). Operates against a structured product profile rather than generic prompts.

## What it is

【事实】A toolkit of 25 marketing-specific AI skills, authored by **Corey Haines** (founder of Conversion Factory) and released under the MIT license as free software. [CH]

## How it works

【事实】Before invocation, the user completes a product-profile questionnaire: [CH]

| Profile field | Purpose |
|---|---|
| Product definition | Anchor what the product is |
| Problem solved | Anchor why the product exists |
| Target audience | Constrain language and channel |
| Competitors | Calibrate differentiation |
| Differentiation | Sharpen positioning |
| Brand tone | Shape voice across outputs |
| Pricing strategy | Inform offer copy and CTAs |

The AI then executes each chosen skill against this profile — outputs are customized to the specific product rather than generic. The author emphasizes "你填的越详细，后面输出的越准" (the more detailed the profile, the more precise the output).

## Coverage areas

【事实】CRO, copywriting, SEO, email marketing, growth, advertising, customer retention. [CH]

## Use pattern

【事实】Users select which skills to run based on current need — there is no requirement to use all 25. [CH]

## Why the profile front-loads value

【推断】The structural insight worth keeping is the **front-loaded profile**, not the 25 skills themselves. Most marketing-AI prompts fail because they ask the model to invent the brand context on every call. A profile-first design solves this once and amortizes the answer across every downstream skill — same input quality for the 1st email and the 50th. The 25 skills are the surface; the profile is the engine. Anyone replicating this pattern (for marketing or any other domain) should copy the profile architecture before copying the skill list.

---

## Related

- [[Minto-This-Skill]] — sibling: also a structural-skill pattern that shifts cognitive load from prompt to framework
- [[Founder-As-KOL]] — adjacent: marketingskills supplies tactical execution power for founder-led marketing
- [[Vibe-Marketing]] — adjacent: marketingskills is one concrete toolkit for the AI-drafts stage of the Vibe-Marketing workflow
- [[Narrative-First-Strategy]] — adjacent: profile fields like brand tone and differentiation are the surface where narrative strategy meets tactical content
