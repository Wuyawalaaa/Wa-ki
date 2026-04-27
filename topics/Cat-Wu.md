---
title: Cat Wu — AI PM Paradigm
type: [person, framework]
aliases: [Cat Wu, cat wu, AI PM, AI PM paradigm, AI PM 新范式, Anthropic Claude Code PM, Claude Code PM, "code is cheap, deciding what to build is expensive", just-right AGI, 95% automation problem, automation valley of death]
tags: []
sources:
  CW: Cat Wu 访谈·AI PM 新范式 — 阿進營業中's Chinese summary of Cat Wu's Lenny's Podcast interview (Xiaohongshu, 2026-04-24) → ../sources/2026-04-26-ajin-cat-wu-ai-pm-paradigm.md
last_updated: 2026-04-26
provenance: mostly-sourced
---

# Cat Wu — AI PM Paradigm

> PM Lead for Anthropic's Claude Code. Six observations from her Lenny's Podcast interview that, taken together, describe how product management changes when the underlying technology iterates weekly instead of yearly. Articulated as "AI PM 新范式" by the Chinese-language summary that captured this material.

## Who

【事实】Cat Wu is the **PM Lead for Anthropic's Claude Code**. The substantive content on this page is drawn from a Lenny's Podcast interview with her, summarized into Chinese by 阿進營業中. [CW]

## Six takeaways

【事实】[CW]

### 1. Accelerated product cycles

Daily/weekly timelines replace 6–12 month planning. Use **"research preview"** labels to ship and test experimental features without committing to long-term support. The label itself is a UX device: it lets the team experiment publicly without the weight of a GA-quality commitment.

### 2. Minimal documentation

PRDs are written only for: ambiguous projects, infrastructure investments, or failure-mode definitions. Weekly metrics + team principles replace most other documentation.

### 3. Decision-making is the bottleneck

> "Code 越来越便宜，贵的是'决定写什么'."
> Code is increasingly cheap; deciding what to build is the scarce resource.

PM hiring at Anthropic favors **engineers with product taste** — i.e., people whose taste-output ratio is high enough to bottleneck on the right problem rather than the implementation.

### 4. "Just-right AGI" approach

Don't build for the future super-model — **maximize the current model's capabilities**. Worked example: Claude Code's todo list evolved from a *memory aid* (when models forgot context across long tasks) into a *progress display* (as model capability improved). Same surface, two different jobs, calibrated to where the model actually is.

### 5. Evaluation-driven development

Writing evals + asking models to **explain their failures** clarifies success metrics and isolates whether problems live in: prompting, tooling, processes, or user education. The diagnostic step ("ask the model why it failed") is the move that turns evals from regression-tests into product-design instruments.

### 6. Automation thresholds — the 95% problem

> 95% automation creates trust issues. Aim for near-100%, or avoid automation entirely.

The 5% surprises break the trust the other 95% built. The middle is the worst place to land — better to fully automate (so the user accepts AI-mediation as the contract) or stay manual (so the user owns the loop).

## Why these hang together

【推断】The six takeaways aren't a random list — they're four mechanisms and two principles that share an underlying premise: **when the underlying technology changes weekly, the PM's job shifts from "specify and ship" to "decide and verify."**

| Cluster | Takeaways | Underlying move |
|---|---|---|
| Velocity machinery | #1 cycles, #2 docs | Cut everything that assumes stable requirements |
| Decision-as-product | #3 bottleneck, #4 just-right AGI | The expensive choice is now *what* to build, calibrated to *current* capability |
| Quality machinery | #5 evals, #6 automation thresholds | When you can't pre-specify, you have to be excellent at post-verification |

Once you see this pattern, the takeaways predict each other: minimal documentation (#2) only works if you have weekly metrics (#1), which only works if your evals are sharp (#5), which only works if you've decided what success means (#3).

## Connections in the wiki

- **#5 evaluation-driven development** is the production-side counterpart to [[Evaluability]] — Nielsen's frame puts evaluability inside the *user's* loop ("can the end user verify this output?"); Cat Wu's frame puts it inside the *team's* loop ("can we verify the model is doing what we wanted?"). Both rest on the same fact: in AI products, verifying-the-output replaces inspecting-the-implementation as the load-bearing quality move.
- **#3 decision-making bottleneck** parallels the [[Articulation-Barrier]] one level up. The barrier for end users is "I can't articulate what I want"; the barrier for PM/founder teams is "we can't decide which articulated thing to build." Same cognitive asymmetry (recognizing > generating), different stakeholder. [[Sell-Before-Build]] is the strategic answer: don't decide alone — let the market reveal the answer cheaply.
- **#6 automation thresholds** is a sharper restatement of the [[Intent-UX]] Plausibility Trap. 95%-automated outputs *look* finished, which is exactly when humans stop checking — and the 5% then breaks the trust silently. The fix isn't "be more accurate"; it's "don't land in the middle." Either own the loop or fully delegate.
- **#4 just-right AGI** has no direct existing peer in the wiki yet but is the strategic counterpart to [[Sell-Before-Build]] for AI products: validate against today's model, not the imagined future one.

【推断】Worth noting the structural parallel to founder content: [[Dan-Koe]]'s 2-hour SOP is "the production-side discipline for solo creators in an AI-content world"; Cat Wu's six takeaways are "the production-side discipline for product teams in an AI-product world." Same pattern (cut docs, automate the cheap parts, invest the saved cycles into the parts where taste / decisions / evaluation can't be automated), different domain.

## Provenance flags

【推断】The Lenny's Podcast primary source was not directly fetched. The numbered structure ("six takeaways") is 阿進營業中's framing of the interview, not necessarily Cat Wu's own framing. Treat the bullet labels as paraphrased; the underlying claims are consistent enough with publicly known Anthropic / Claude Code positioning that they're credible directionally, but a direct podcast listen would be needed to lock specific phrasings.

---

## Related

- [[Evaluability]] — user-side verification; Cat Wu's takeaway #5 is the team-side counterpart
- [[Articulation-Barrier]] — Cat Wu's takeaway #3 is the same cognitive asymmetry one level up
- [[Sell-Before-Build]] — strategic answer to the decision-making bottleneck
- [[Intent-UX]] — parent paradigm where the Plausibility Trap (and takeaway #6) live
- [[Dan-Koe]] — structural parallel for solo content; same "cut what's automatable, invest saved cycles in taste/decisions" pattern
