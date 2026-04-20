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

---

## 5. Inbox Digestion Flow

Triggered by: "消化 inbox" / "digest inbox" / "整理一下 inbox" / similar.

**Steps:**

1. Read `inbox.md` top to bottom.
2. For each distinct item (URL, quote, screenshot, note, Hermes block):
   - **If URL:** WebFetch the content. If auth-walled (login required), note this and ask Luna to paste content manually or skip.
   - **If `[Hermes/*]` block:** treat per §7.
   - **If image path:** copy reference to `sources/images/`, summarize image content via vision.
   - Archive fetched content to `sources/YYYY-MM-DD-<slug>.md`.
   - Determine target: existing topic file, `uncategorized.md`, or propose new topic (see §3).
   - Integrate using §4 style conventions.
3. Flag uncertain categorizations — list them explicitly and ask Luna.
4. If `project-snapshots/` has content AND new concepts were added → generate **proposals** in the digest chat report (see §6.3). Do NOT modify bridge files.
5. Move processed `inbox.md` content to `archive/inbox/YYYY-MM-DD.md`. Clear active inbox.
6. Git commit: `digest: YYYY-MM-DD — N items, topics: <list>`.
7. Summary report: what was integrated where, what's pending review.

---

## 6. Snapshot, Bridge & Proposal Protocol (Phase 2 — currently dormant)

Activates when `project-snapshots/` contains files.

### 6.1 Snapshot (mirrors project state)

**Purpose:** A read-only summary of a project folder, so the wiki knows what the project currently looks like without re-reading every file.

**Triggers:**
- **T1 Pre-digest check:** Before inbox digestion, check mtime of all files in projects with snapshots. If any project file is newer than its snapshot → report and offer refresh.
- **T2 Session startup:** Same check on every new Claude Code session.
- **T3 Explicit:** "refresh [project] snapshot" → rebuild from scratch.

**File shape:** `project-snapshots/<project>-YYYY-MM-DD.md` contains:
- One-line summary per project document
- Key concepts used
- Section outlines
- File list with mtimes

### 6.2 Bridge (factual usage record — lazy, explicit only)

**Purpose:** Records what wiki materials Luna *actually referenced* when producing a specific piece of project work. Historical, not speculative. Lets Luna trace "which ideas fed into which deliverable" and re-audit execution if the underlying knowledge evolves.

**Triggers (explicit only):**
- **T3 Explicit:** "update [project] bridge" / "record this in the bridge" / similar → append/update entries for the work Luna names.
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
# <Topic Name>
> <One-sentence description of scope>
> Last digested: YYYY-MM-DD

## <Concept 1>

【事实/推断】 <core statement in one sentence>

<elaboration, context, nuance — only what's needed>

### Sources
- [<title>](../sources/YYYY-MM-DD-<slug>.md)

### Related
- [[<other-topic>#<section>]]

---

## <Concept 2>
...
```

---

## 12. When In Doubt

- **Uncertain categorization?** → `uncategorized.md`, flag for Luna.
- **Uncertain intent?** → ask before acting.
- **Task seems to require forbidden access?** → refuse and explain.
- **Judgment call not covered here?** → ask Luna. If the answer has long-term value, propose amending this CLAUDE.md.

---

## 13. Non-negotiables

- Never write outside `~/Desktop/wiki LLM/` without explicit Luna approval per operation.
- Never silently delete anything — always offer `archive/` first.
- Never "clean up" wiki structure on your own initiative — propose, wait, execute.
- Never embed project-specific references inside topic files — those belong in `project-bridges/` only.
- Never modify this CLAUDE.md without Luna's explicit approval.
