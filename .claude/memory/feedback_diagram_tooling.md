---
name: feedback-diagram-tooling
description: Mermaid cannot do circular/radial layouts in Obsidian notes for this vault — hit and confirmed 2026-08-09
metadata:
  type: feedback
---

Mermaid's flowchart engine (dagre-based) only supports hierarchical layouts (top-down or left-right) — it **cannot** render a true circular/radial arrangement of nodes. Discovered when trying to recreate a 5-node "vicious circle" diagram from a source image; a hand-coded inline SVG with manually computed coordinates was tried first and rejected by the user as low quality, then Mermaid was tried and hit this same layout limitation.

Also: Mermaid code fences (` ```mermaid `) will **not** render if nested inside a raw HTML block (e.g. inside a `<div>...</div>`) in this vault's Obsidian notes — they must sit as standalone markdown, blank-line-separated from surrounding HTML, consistent with the vault's general "don't mix markdown inside raw HTML" rule already in `CLAUDE.md`.

**Resolution used:** For that specific diagram, the user chose to drop the diagram entirely and use a plain styled numbered list instead (each factor as a list item with its stat, plus a closing line noting it "closes the loop" back to the first item) — see the "Vicious Circle" section in `notes/GS2/Social Justice.md` (Mental Healthcare section) for the pattern.

**How to apply:** Don't reach for Mermaid when a circular/radial diagram is wanted in this vault. Options in order of likely acceptance: (1) ask whether a plain styled list is acceptable instead, (2) offer a properly-built SVG only if the user wants to invest in getting exact coordinates right, (3) Mermaid only for genuinely hierarchical/sequential flows.
