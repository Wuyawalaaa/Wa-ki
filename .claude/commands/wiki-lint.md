Run the wiki health check defined in §12 of CLAUDE.md.

Scan for:
1. Contradictions — opposing claims about the same concept across pages
2. Stale claims — old claims not updated after later sources arrived
3. Orphans — topic files nothing links to
4. Missing concept pages — concept names repeated across 3+ files with no page of their own
5. Broken cross-refs — `[[wikilink]]` targets that don't exist (resolve through `aliases:` before flagging)
6. Provenance drift — frontmatter `provenance:` disagreeing with actual body composition
7. Coverage gaps — topics Luna shows repeated interest in but wiki covers thinly

Output: chat report grouped by category, each finding with file path, severity (high/medium/low), and suggested action. Do NOT modify any files — lint only reports.
