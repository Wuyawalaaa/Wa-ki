Run the inbox digestion flow defined in §5 of CLAUDE.md.

Read `inbox.md`, process each item per the prefix detection table (auto-ingest / review / thoughts routing), run mandatory dedup check before writing to `topics/`, apply three-voice tagging with inline `[XX]` citations, run cross-linker pass, archive + clear inbox, commit, and emit the summary report.

Stop and ask if any item needs a judgment call you can't make alone.
