---
name: feedback-card-row-style
description: Named visual style ("card row") the user invokes by name for rendering extracted infographics as a horizontal row of stat/category cards
metadata:
  type: feedback
---

The user coined the nickname **"card row"** for a specific visual pattern used throughout `notes/GS2/Social Justice.md` to represent extracted infographic content (hub-and-spoke diagrams, multi-category comparisons, stat groupings). When asked to "use card row style" (or "in row card style"), build:

- A `<table>` with one `<tr>` and N `<td>` columns (equal width via `width:X%` + `table-layout:fixed`), `border-collapse:separate; border-spacing:6–8px`.
- Each cell holds a white card (`<div>`): a colored header banner on top (category/label, centered text) and a bulleted or stat body below, `display:flex; flex-direction:column`.
- **All header banners share one fixed height** (e.g. `height:38px`) with `display:flex; align-items:center; justify-content:center` so 1-line and wrapping 2-line titles look identical.
- **All card bodies share one fixed height** too (e.g. `height:150–290px` depending on content length) — do NOT rely on `height:100%` (unreliable in Obsidian's renderer); set an explicit pixel height on every card in the row instead.
- Header colors cycle through the vault's established palette: teal `#2c7a6b` → orange `#d68910` → purple `#8e44ad` → blue-grey `#4a6b7c` → red `#c0392b`, repeating for >5 columns. Border color on each white card is a light tint matching its header.
- For >4–5 columns, shrink font/padding (e.g. `font-size:0.76–0.78em`) and increase height instead of shrinking to illegibility.
- Comma-separated items within one bullet should be split into separate `<li>` bullets if asked ("split the commas with more bullet points").

**When NOT to use it:** the user has also asked to convert card-row layouts *back* into plain two/three-column tables ("Function | Description", "Key Feature | Challenge" paired columns) when the content is more tabular/comparative than categorical — card row is for genuinely categorical groupings (hub-and-spoke diagrams, "why X matters" style infographics), plain tables are preferred for structured comparisons. Ask-by-example if unsure; default to whichever the user's most recent similar request used.

**Why:** The user asked me to name this style specifically so they could invoke it by name going forward, and used it as the default treatment for most extracted infographics across the Health and Education sections.

**How to apply:** Whenever the user says "card row" / "row card style", or pastes a hub-and-spoke / multi-category infographic without specifying a format, default to this pattern.
