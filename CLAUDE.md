# wiki LLM — Operating Instructions

This file is auto-loaded by Claude Code whenever a session starts in this folder. These rules govern how you (Claude Code) maintain this wiki.

---

## 1. Identity

**What this is:** Luna's personal general-knowledge wiki. A library of concepts, theories, frameworks, cases, and intellectual raw material she encounters across all her work.

**What this is NOT:** Any specific project's strategy, execution plan, or PRD. Project-specific content lives in separate project folders (e.g., `~/Desktop/Clinamen X/`).

Wiki content should remain **project-agnostic**. Do not embed references to specific projects inside topic files — such linkage lives exclusively in `project-bridges/` (see §6).

---

## 2. Permission Boundaries

### Writable (no approval needed)
- Anything inside `~/Desktop/wiki LLM/`

### Readable (only when explicitly requested or listed in `project-snapshots/`)
- Project folders Luna has explicitly named (currently: `~/Desktop/Clinamen X/`)

### Forbidden
- Writing to ANY path outside `~/Desktop/wiki LLM/`
- Reading `~/Desktop/` items Luna has not explicitly authorized — especially personal files (wedding, visa, payslips, medical, rental, passport photos, `Marital RFE/`, etc.)

### `inbox.md` is a symlink to iCloud
- `~/Desktop/wiki LLM/inbox.md` is a symbolic link. The real file lives at `~/Library/Mobile Documents/com~apple~CloudDocs/wiki-llm-inbox.md`.
- Why: so Luna can append from iPhone via iCloud sync.
- For Claude: transparent — read/write/edit on the `inbox.md` path work as normal; the filesystem resolves through the symlink. No special handling needed.
- Scope note: this one symlinked file is the only writable path that physically lies outside `~/Desktop/wiki LLM/`. The permission model is still "one conceptual folder"; the iCloud location is a plumbing detail.

**Enforcement:** If a task seems to require writing outside this folder, STOP. State the exact path you would write to, explain why, and wait for Luna's explicit `ok`.

---

## 3. Structure Philosophy

**Emergent, not pre-planned.**

- Begin with everything flowing into `uncategorized.md`.
- **Topic split threshold:** When 3+ items in `uncategorized.md` share a theme → propose a new `topics/<name>.md`. Wait for approval before creating.
- **Folder upgrade threshold:** When a topic file accumulates 5+ differentiable sub-themes (or exceeds ~1000 lines) → propose upgrading to `topics/<name>/` folder with `index.md` + sub-files. Wait for approval.
- **Merge:** When two topic files overlap substantially or reference each other repeatedly → propose merging. Wait for approval.
- **Delete:** Default to moving into `archive/`, not real deletion. Only delete for real when Luna says "permanently delete" or "真删".

**Principle:** Wiki shape should reflect how Luna's thinking has evolved, not a pre-imposed taxonomy.

---

## 4. Style Conventions

Luna's existing writing style (mirror it):

- **Tables for structured comparison.** Prefer tables over prose when comparing options, listing attributes, or tracking status.
- **`【事实】` tag** — for facts with clear source citation.
- **`【推断】` tag** — for interpretations, inference, speculation, or judgment calls.
- **Every concept cites its source.** Link back to `sources/` files.
- **Cross-references** use `[[filename#section]]` inline or `[text](relative/path.md)` for prose.
- **Concise over verbose.** No filler. No meta-commentary about what you're about to say.
- **Multilingual.** Match source material language when quoting. Otherwise English for precision, Chinese when Luna prefers or concept emerged in Chinese first.

### File naming
- `sources/YYYY-MM-DD-<slug>.md` — **kebab-case** slug (e.g. `2026-04-20-karpathy-gist.md`). Dated, one-off archives.
- `topics/<Concept-Name>.md` — **TitleCase-With-Hyphens** (e.g. `Strength-Of-Intent.md`, `Narrative-First-Strategy.md`). Stable concept entries.
- Rationale: a glance at a `[[wikilink]]` tells you whether it points to a dated source archive or a canonical concept page.

### Frontmatter (required on every topic file)
Schema (see §11 for the full template): `title`, `type`, `tags`, `sources`, `last_updated`, `provenance`.

- `provenance: mostly-sourced | mixed | mostly-inference` — the page's overall lean.
- **Page-level `provenance` does NOT replace per-claim `【事实】`/`【推断】` tagging.** Both coexist:
  - Frontmatter `provenance` = *what the page leans toward as a whole*.
  - Inline `【事实】`/`【推断】` = *which specific claim* is grounded vs inferred.
- A `mostly-sourced` page can still contain `【推断】` lines; a `mostly-inference` page can still have `【事实】` anchors. The two layers together let Luna scan for overall reliability (frontmatter) and audit individual claims (inline).

### Tags (controlled vocabulary)
- Approved tags live in `_meta/taxonomy.md`. That file doesn't exist yet; create on first tag use.
- New tags require Luna's explicit OK before being added. Prevents drift (`mev` vs `MEV` vs `miner-extractable-value` silently coexisting).
- When proposing a new tag, check `_meta/taxonomy.md` for near-matches first; if close, suggest using the existing one.

---

## 5. Inbox Digestion Flow

Triggered by: `/wiki-ingest` / "消化 inbox" / "digest inbox" / "整理一下 inbox" / similar.

**Steps:**

1. Read `inbox.md` top to bottom.
2. For each distinct item (URL, quote, screenshot, note, Hermes block):
   - **If URL:** WebFetch the content. If auth-walled (login required), note this and ask Luna to paste content manually or skip.
   - **If `[Hermes/*]` block:** treat per §7.
   - **If image path:** copy reference to `sources/images/`, summarize image content via vision.
   - Archive fetched content to `sources/YYYY-MM-DD-<slug>.md`.
   - Determine target: existing topic file, `uncategorized.md`, or propose new topic (see §3).
   - Integrate using §4 style conventions.
3. **Cross-linker pass.** After all items are integrated, scan the full wiki for plain-text mentions of existing topic titles that aren't yet `[[wikilinked]]`; wrap matches. Skip mentions inside code blocks, inside `sources/` (archival), and inside already-linked spans. Report the count of links inserted.
4. Flag uncertain categorizations — list them explicitly and ask Luna.
5. If `project-snapshots/` has content AND new concepts were added → generate **proposals** in the digest chat report (see §6.3). Do NOT modify bridge files.
6. Move processed `inbox.md` content to `archive/inbox/YYYY-MM-DD.md`. Clear active inbox.
7. Git commit: `digest: YYYY-MM-DD — N items, topics: <list>`.
8. Summary report: what was integrated where, what's pending review.

---

## 6. Snapshot, Bridge & Proposal Protocol (Phase 2 — currently dormant)

Activates when `project-snapshots/` contains files.

### 6.1 Snapshot (mirrors project state)

**Purpose:** A read-only summary of a project folder, so the wiki knows what the project currently looks like without re-reading every file.

**Triggers:**
- **T1 Pre-digest check:** Before inbox digestion, check mtime of all files in projects with snapshots. If any project file is newer than its snapshot → report and offer refresh.
- **T2 Session startup:** Same check on every new Claude Code session.
- **T3 Explicit:** `/wiki-snapshot-refresh [project]` / "refresh [project] snapshot" → rebuild from scratch.

**File shape:** `project-snapshots/<project>-YYYY-MM-DD.md` contains:
- One-line summary per project document
- Key concepts used
- Section outlines
- File list with mtimes

### 6.2 Bridge (factual usage record — lazy, explicit only)

**Purpose:** Records what wiki materials Luna *actually referenced* when producing a specific piece of project work. Historical, not speculative. Lets Luna trace "which ideas fed into which deliverable" and re-audit execution if the underlying knowledge evolves.

**Triggers (explicit only):**
- **T3 Explicit:** `/wiki-bridge-update [project]` / "update [project] bridge" / "record this in the bridge" → append/update entries for the work Luna names.
- **Reconciliation:** After a snapshot refresh, if paths or section titles in existing bridge entries became stale → offer to reconcile (rename references, flag broken links). Do NOT add new entries during reconciliation.

**Do NOT auto-update bridges** when new wiki content is added. New wiki material existing ≠ it was used. Bridge entries are written only when Luna confirms usage.

**File shape:** `project-bridges/<project>.md` contains:
- Mapping: project deliverable/section → wiki concepts that informed it (with dates)
- Reverse index: wiki concept → where Luna applied it in this project

**Critical:** Bridges live in wiki side only. Never write back to project folders.

### 6.3 Proposals (chat-only, no file)

**Purpose:** Dual-purpose — (a) give Luna a heads-up that newly digested material *might* connect to existing project work, (b) let Luna verify whether Claude actually understood the material (if the reasoning is off, the comprehension is off).

**Trigger:** After inbox digest, if `project-snapshots/` is non-empty AND new concepts were added to the wiki → emit proposals inline in the digest chat report. Nothing is written to disk.

**Proposal format (in chat):**
```
## Proposals — possible project connections

### [new wiki concept / file]
- **Possibly relates to:** [project]/[snapshot section or deliverable]
- **Reasoning:** [one sentence explaining the link — this is the comprehension check]
- **Confidence:** low / medium / high

(repeat per concept)
```

**After Luna reviews:**
- If she confirms a proposal is real AND wants it recorded → that's a T3 bridge update (§6.2).
- If she says the reasoning is off → note the correction, re-read source if needed, don't record anything.
- If she ignores them → they vanish with the chat. That's fine; they're ephemeral by design.

---

## 7. Hermes / Gemini Inputs

Luna runs a separate Hermes Agent on her MacBook (in `~/Desktop/hermes/`) using Gemini as its LLM brain. Hermes handles low-importance research batch tasks.

### Hermes's writable scope
Hermes is permitted to write ONLY to `~/Desktop/wiki LLM/inbox.md` (append mode). Never to topics, sources, snapshots, or anywhere else in the wiki.

### Format Hermes uses
```
## [Hermes/Gemini-<model>] YYYY-MM-DD HH:MM

**任务**: <what Luna asked>
**产出**:
<research output>

**来源**:
- <url 1>
- <url 2>

---
```

### Handling Hermes entries during digest
- Treat with **higher skepticism** than Luna's direct input.
- Re-fetch at least 1-2 critical source links to spot-verify facts.
- Tag Gemini's synthesized conclusions as `【推断】`, not `【事实】` — even when Gemini sounds confident.
- Preserve Gemini's perspective; note it came from Hermes/Gemini in the source archive.
- If Gemini's claim contradicts existing wiki content, flag the contradiction for Luna.

---

## 8. Session Startup Protocol

Every new Claude Code session in this folder:

1. If `project-snapshots/` has snapshots → run T2 check → report stale projects.
2. If `project-bridges/` has bridges > 14 days old → offer refresh.
3. If `inbox.md` is non-empty → report item count and latest entry timestamp. **Do NOT auto-digest.**
4. Proceed with Luna's request.

---

## 9. Operations Requiring Luna's Approval

Always present a plan and wait for explicit `ok` / `好` / similar before executing:

- Creating a new top-level topic file
- Splitting a topic file into a folder
- Merging topic files
- Moving content between topics
- Any deletion — even to `archive/`
- Refreshing snapshots
- Writing to any path outside `~/Desktop/wiki LLM/` (normally forbidden, §2)
- Large structural reorganization
- Bulk rewrites of existing content

---

## 10. Operations Auto-allowed (no approval)

- Appending to existing topic files during inbox digestion
- Moving clearly-fitting items from `uncategorized.md` to existing topic files
- Archiving sources and inbox items
- Git commits of your own changes
- Answering Luna's direct questions about wiki content
- Reading existing wiki files

---

## 11. Topic File Template

```markdown
---
title: <Topic Name>
type: concept | framework | case-study | person | other
tags: [tag1, tag2]
sources:
  - ../sources/YYYY-MM-DD-<slug>.md
last_updated: YYYY-MM-DD
provenance: mostly-sourced | mixed | mostly-inference
---

# <Topic Name>
> <One-sentence description of scope>

## <Concept 1>

【事实/推断】 <core statement in one sentence>

<elaboration, context, nuance — only what's needed>

### Sources
- [<title>](../sources/YYYY-MM-DD-<slug>.md)

### Related
- [[<Other-Topic>#<section>]]

---

## <Concept 2>
...
```

---

## 12. Lint / Health Check

**Purpose:** Ingestion is additive — it only adds. Lint is the periodic compaction pass that catches what silently accumulates: contradictions, orphans, stale claims, missing concept pages, weak cross-linking, provenance drift, coverage gaps.

### Trigger
- Explicit only: `/wiki-lint` / "lint the wiki" / "wiki 体检" / "check for drift".
- No auto-trigger. Lint surfaces issues that need Luna's decisions; running it unprompted would spam.

### What lint checks
1. **Contradictions** — two topic files making opposing claims about the same concept.
2. **Stale claims** — claims superseded by newer sources ingested later but not back-propagated.
3. **Orphans** — topic files nothing links to (effectively lost to query).
4. **Missing concept pages** — concept names repeated across 3+ topic files but lacking their own page.
5. **Broken cross-refs** — `[[wikilink]]` targets that don't exist (renamed/deleted).
6. **Provenance drift** — pages whose frontmatter `provenance:` says `mostly-sourced` but whose body is mostly `【推断】` (or vice versa).
7. **Coverage gaps** — areas where Luna has expressed ongoing interest (via inbox frequency or explicit mention) but the wiki has thin coverage.

### Output format
A chat report, grouped by category. Each finding lists:
- File path (+ line number where applicable)
- Severity: high (contradiction / broken ref) / medium (drift / orphan) / low (gap / missing page)
- Suggested action

**No files are modified during lint.** Lint only reports.

### After Luna reviews
- She decides per finding: fix / defer / ignore.
- Non-trivial content edits go through §9 approval.
- Trivial fixes (broken link rename, inserting a missing `[[wikilink]]`) proceed auto per §10.

---

## 13. When In Doubt

- **Uncertain categorization?** → `uncategorized.md`, flag for Luna.
- **Uncertain intent?** → ask before acting.
- **Task seems to require forbidden access?** → refuse and explain.
- **Judgment call not covered here?** → ask Luna. If the answer has long-term value, propose amending this CLAUDE.md.

---

## 14. Slash Commands (index)

Canonical commands Luna can invoke. Each one references the section that defines full behavior.

| Command | Args | Purpose | Defined in |
|---|---|---|---|
| `/wiki-ingest` | — | Digest inbox: fetch → archive → categorize → integrate → cross-link → propose | §5 |
| `/wiki-query` | `<question>` | Answer a question from wiki content with citations | ad-hoc |
| `/wiki-lint` | — | Health check: contradictions, orphans, stale, missing pages, broken refs, drift, gaps | §12 |
| `/wiki-crosslink` | — | Run cross-linker pass standalone (normally auto-runs in `/wiki-ingest` step 3) | §5 step 3 |
| `/wiki-snapshot-refresh` | `[project]` | Rebuild project snapshot from scratch | §6.1 |
| `/wiki-bridge-update` | `[project]` | Record bridge entries for confirmed wiki→project usage | §6.2 |
| `/wiki-status` | — | Quick report: inbox count, uncategorized count, last digest, snapshot/bridge ages | ad-hoc |

**Implementation in Claude Code:** slash commands are markdown files at `.claude/commands/<name>.md`. The file content is the prompt Claude runs when invoked. Luna can add / edit / delete commands anytime — nothing is locked in, and the file format is plain markdown.

**Current state:** this table is the spec; the `.claude/commands/` files don't exist yet. Natural-language triggers (e.g. "消化 inbox") still work regardless of whether the slash-command files are created.

---

## 15. Non-negotiables

- Never write outside `~/Desktop/wiki LLM/` without explicit Luna approval per operation.
- Never silently delete anything — always offer `archive/` first.
- Never "clean up" wiki structure on your own initiative — propose, wait, execute.
- Never embed project-specific references inside topic files — those belong in `project-bridges/` only.
- **Never silently overwrite contradictions.** If a new source contradicts existing wiki content, flag the conflict and let Luna decide (keep old / keep new / reconcile / keep both with context). Never resolve it on your own.
- Never modify this CLAUDE.md without Luna's explicit approval.
