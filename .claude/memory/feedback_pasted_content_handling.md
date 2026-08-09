---
name: feedback-pasted-content-handling
description: How to handle garbled/interleaved pasted PDF text and OCR artifacts when building notes in this vault
metadata:
  type: feedback
---

When the user pastes text extracted from a PDF or slide (often two-column layouts), the content frequently comes through **interleaved mid-sentence** — e.g. an "Effectiveness" column and a "Limitations" column, or a sidebar callout box, get mixed into one paragraph. When this happens: untangle it into the correct separate sections/columns before writing it into the note, rather than reproducing the jumble as-is. Flag to the user afterward that untangling was done, briefly, in case the reconstruction was wrong.

Similarly, pasted content very often contains a stray **"Student Notes:"** fragment (an artifact from wherever the user is copying from) sitting mid-heading or mid-sentence. Drop it silently while writing the content, then mention in the reply that it was dropped — don't ask permission first, don't leave it in.

**Why:** Confirmed repeatedly across many turns in a long session (2026-08-09) building out `notes/GS2/Social Justice.md` — the user never objected to either behavior and kept sending more garbled/artifact-laden pastes expecting the same handling.

**How to apply:** Any time pasted source text looks like it has two unrelated topics running together, or has "Student Notes:" (or similar obvious copy artifacts) embedded, clean it up proactively rather than asking first — just note what was done afterward.
