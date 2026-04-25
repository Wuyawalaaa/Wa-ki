---
title: Sell-Before-Build
type: [framework, methodology]
aliases: [先卖后建, sell before build, pre-sell validation, sell-before-you-build, Sell-Before-Build Validation]
tags: []
sources:
  TH: Tyler Hogge via Xiaohongshu (2026-04-21) → ../sources/2026-04-21-tyler-hogge-sell-before-build.md
  RW: Reddit AI projects use waitlists to validate demand, via Xiaohongshu (2026-04-25) → ../sources/2026-04-25-reddit-waitlist-validation.md
last_updated: 2026-04-25
provenance: mostly-sourced
---

# Sell-Before-Build

> 先卖后建：在工程开发开始之前，通过真实销售对话验证需求的低成本方法。

## 核心论点

【事实】初创公司最大的风险不是缺钱，而是花半年造出来的东西没人要。Sell-Before-Build 把「拒绝」前置、把「投入」后置 —— 先找到愿意买的客户，再决定造什么。[TH]

## 7 步框架

【事实】[TH]

| 步 | 动作 |
|---|---|
| 1 | 建立独特见解（unique insights）|
| 2 | 做出 Figma 视觉原型 |
| 3 | 安排 30 次销售对话 |
| 4 | 直接提出购买请求（不是"你觉得有用吗"）|
| 5 | 根据反馈迭代 |
| 6 | 反复直到达到 30% 转化率 |
| 7 | 市场验证完成，才进入工程开发 |

## 30% 转化率门槛

【事实】达到 30% 转化率即说明找到了"市场迫切感"（market urgency），是进入工程开发的绿灯信号。[TH]

【推断】30% 的门槛颇激进。B2B 冷启动销售常见转化率远低于此；前提可能是"经过精心筛选的目标客户名单 + 明确的 pain point"，而非泛漫找人。使用时需根据行业和客户画像调整。

## 经典案例

【事实】[TH]

- **Flexport** — 用假网站让富士康等大公司注册，在写代码之前就验证了货代软件的需求。
- **Redo** — 用 $100 waitlist 验证需求。

## Channel — waitlists on Reddit for AI projects

【事实】A common pre-product validation pattern observed on Reddit (see also [[Reddit-First-Acquisition]] for the broader bootstrapped-channel thesis): many founders pair a simple concept with a waitlist to test market interest, instead of shipping an actual product. The waitlist's stated value is twofold — collect feedback before building, and filter high-intent users from passive interest. "真正的价值在于收集反馈和筛选用户，而非最终成品." [RW]

【推断】This is the same move SBB names as one of "waitlist deposit, free pilot, consultative call" (see Luna's note below). What Reddit adds as a channel: the audience self-selects for technical curiosity and AI tolerance, which compresses the targeting work. The risk on Reddit specifically is that signups skew toward signal-watchers rather than buyers — Reddit's high-intent moments are about *interest in trying*, not *commitment to pay*. Useful for the feedback half of the goal; weaker for the willingness-to-pay half SBB's 30 sales conversations are designed to surface.

## Relationship to Narrative-First

【Luna】SBB and [[Narrative-First-Strategy]] aren't two separate things — they're two focal points of the same thing (pre-product credibility / commitment-capital accumulation), not strict trade-offs. Narrative does reach; SBB converts a portion of that reach into high-density commitment. People willing to commit have to come from a larger audience first, so reach is *upstream* of commitment, not a substitute for it. Between them sits a conversion rate, and the number depends on the specific methods for going deep with target people and getting them to actually commit — SBB's 7-step framework is one such method; waitlist deposit, free pilot, consultative call are others, each with different conversion rates.

---

## Related

- [[Narrative-First-Strategy]] — same problem, upstream view (does reach; supplies the audience that commitment conversion draws from)
- [[Reddit-First-Acquisition]] — Reddit as the highest-leverage channel for bootstrapped pre-product validation
