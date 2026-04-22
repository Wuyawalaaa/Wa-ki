Rebuild the project snapshot defined in §6.1 of CLAUDE.md.

Project: $ARGUMENTS

Read the named project folder (must be explicitly authorized per §2 — e.g. `~/Desktop/Clinamen X/`). Build `project-snapshots/<project>-YYYY-MM-DD.md` containing:
- One-line summary per project document
- Key concepts used
- Section outlines
- File list with mtimes

After refresh, if existing bridge entries reference paths or section titles that became stale, offer to reconcile (do NOT auto-add new bridge entries).
