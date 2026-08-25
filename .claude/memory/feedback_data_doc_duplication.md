---
name: feedback-data-doc-duplication
description: Any statistic added to a topic note must also be logged in the matching data/ doc — and kept inline in the note too, not replaced by a link
metadata:
  type: feedback
---

When adding numeric stats/figures to a topic note (e.g. `notes/GS2/Social Justice.md`), always also log the same figure as a card in the matching `notes/data/*.md` doc (health.md, education.md, poverty.md, etc.), following the data-sheet card style in `CLAUDE.md`. Do this proactively — the user does not need to ask each time; treat "any data must go to the data doc" as a standing rule for this vault.

**Important nuance on inline figures:** the user tried the "strip the number from the note, replace with 'see [[health]] (data folder)'" pattern early on, but repeatedly reversed it — e.g. "No [[health]] link, just add it the words I have pasted" and "In earlier text it was mentioned rural as well as urban... just add the figures where it was referred." The settled behavior is: **keep the actual figure inline in the note's prose**, and *additionally* duplicate it into the data doc — do not strip it down to a bare link. A `[[health]]`/`[[education]]`/`[[poverty]]` link plus "for these figures" is fine to add as a citation-style footer *alongside* the inline number, not as a replacement for it.

**Discrepancies:** when a newly-pasted figure conflicts with one already in the note/data doc (different source, different year), flag it inline in both places with a short "Note: conflicts with X — not reconciled" line. Never silently overwrite or silently pick one. See [[project-social-justice-draft-state]] for the running list of unresolved conflicts.

**Why:** Confirmed repeatedly across the 2026-08-10–18 sessions building out Health/Education/Poverty content — the user wants the note itself to remain a complete, readable reference (not gutted into "see elsewhere" stubs), while the data docs serve as the fully-sourced, comparable stat repository.

**How to apply:** Any time you add a paste containing a percentage, count, ₹/crore figure, or ranking to the Social Justice note (or any future topic note in this vault), mirror it into the relevant data doc in the same turn, without being asked.
