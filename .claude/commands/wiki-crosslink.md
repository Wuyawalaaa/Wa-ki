Run the cross-linker pass standalone (normally auto-runs as §5 step 6 after ingest).

Scan the full wiki for plain-text mentions of existing topic titles / aliases that aren't yet `[[wikilinked]]`, and wrap matches.

Rules:
- Skip code blocks
- Skip `sources/` content (sources are raw archives, don't modify)
- Skip already-linked spans
- Check against both `title:` and every entry in `aliases:` across all topic pages

Report: count of links added, list of files touched.
