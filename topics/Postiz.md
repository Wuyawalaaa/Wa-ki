---
title: Postiz
type: [tool, software]
aliases: [postiz, postiz-app, gitroomhq/postiz-app]
tags: []
sources:
  SE: Sealos 开源社区 via Xiaohongshu (2026-04-17) → ../sources/2026-04-21-sealos-postiz-intro.md
  PH: Postiz GitHub README (gitroomhq/postiz-app, 2026-04-21) → ../sources/2026-04-21-postiz-github-readme.md
last_updated: 2026-04-21
provenance: mostly-sourced
---

# Postiz

> 开源多平台社交媒体排期 + AI 内容工具，自我定位为 Buffer / Hypefury / Twitter Hunter 的开源替代品。

## 概述

【事实】Postiz 是一个开源的多平台社交媒体排期工具，官方 README 自述为 "The ultimate social media scheduling tool, with a bunch of AI"。AGPL-3.0 许可证。[PH]

【事实】GitHub 上 29.2k stars / 5.3k forks / 193 releases，最新版本 v2.21.6（2026 年 4 月）。[PH]

【推断】Sealos 开源社区在 2026-04-17 的 Xiaohongshu 推介时引用的是 10.5k+ stars，说明该项目在近期增长显著（约一周内 ~3x）。[SE]

## 支持平台

【事实】Instagram、YouTube、Dribbble、LinkedIn、Reddit、TikTok、Facebook、Pinterest、Threads、X (Twitter)、Slack、Discord、Mastodon、Bluesky。[PH]

## 核心功能

【事实】[PH]

| 类别 | 功能 |
|---|---|
| 排期 | 多平台内容 scheduling |
| AI | 内容生成 |
| 分析 | 效果度量 |
| 协作 | 团队评论与共享 |
| 集成 | API 访问，与 N8N / Make.com / Zapier 对接 |
| 获客 | Lead capture |
| OAuth | 使用官方 OAuth，不需用户分享 API 凭据 |

## 技术栈与部署

【事实】NextJS + NestJS + Prisma (PostgreSQL) + Temporal；monorepo（pnpm workspaces）；提供 Docker Compose 与 dev container 配置。[PH]

【事实】Sealos 方案称可 60 秒内完成部署。[SE]

## 定位

【事实】README 显式将 Postiz 定位为 Buffer / Hypefury / Twitter Hunter 的开源替代品，核心差异点是开源 + 可自托管。[PH]

【推断】对需要 founder-as-KOL 级别内容节奏（参 [[Founder-As-KOL]] / [[Narrative-First-Strategy]]）的个人运营，Postiz 的价值主要在「多平台一点发多点」的时间节省，而非替代人工做内容本身。AI 生成能力存在但需注意 [[Narrative-First-Strategy]] 所述的 AI 过度使用反效果。

---

## Related

- [[Founder-As-KOL]]
- [[Narrative-First-Strategy]]
