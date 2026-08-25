---
name: feedback-draft-promotion-batching
description: Default to strict one-file-at-a-time draft promotion per CLAUDE.md, but honor an explicit blanket approval to batch-promote everything at once
metadata:
  type: feedback
---

`CLAUDE.md`'s draft-first workflow says promotion must go item-by-item with explicit approval per file. That remains the *default*. But when the user gives an explicit blanket instruction — e.g. "approving for all docs", or later "Save the draft to notes and commit and push to repo" after multiple drafts had accumulated — treat that as authorization to promote every pending draft file in one pass (copy to `notes/`, delete from `drafts/`, all in the same turn) rather than re-asking file-by-file.

Also applies to the promote→commit→push chain: once files are promoted, staging/committing/pushing to the GitHub remote in the same turn is fine when the user says "commit and push" — no need to re-confirm each step separately, per [[reference-github-repo]].

**Why:** Confirmed three times — the user explicitly overrode the strict per-file default each time a batch of drafts had built up (data docs + report stubs; the two new policy notes; then Pax Indica + International Groups + International Organisations + a Child Labour policy edit, 2026-08-25), rather than wanting to click through approval for each file.

**How to apply:** Still show/describe the first item and wait for approval when nothing has been said about batching. The moment the user says anything like "approve all", "promote everything", or directly asks you to save-and-commit a known set of drafts, switch to batch mode for that request.
