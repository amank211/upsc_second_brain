# Second Brain — Study Vault

This is a personal study vault for UPSC preparation (and general note-taking).
Follow these rules on every task.

## Folder roles
- `notes/`   — reviewed, trusted notes. This is my revision material.
- `drafts/`  — new AI-generated or in-progress notes, not yet reviewed.
- `sources/` — raw source material (articles, PDFs, extracted text). Reference only.
- `daily/`   — one file per day (`YYYY-MM-DD.md`) for daily current-affairs notes.
- `index.md` — top-level map of all topic notes.

## Reference material
- `sources/syllabus/prelims/paper1.md`, `paper2.md` and
  `sources/syllabus/mains/essay.md`, `GS1.md`–`GS4.md` — official UPSC Civil
  Services Examination syllabus, one file per paper, extracted from a source
  PDF. Use these to check GS paper relevance when tagging or organizing notes.

## Edit rules (important — follow strictly)
- Never delete a file. If something looks obsolete, ask me first.
- Never edit files in `notes/` directly unless I explicitly say "edit the note in
  notes/, not drafts/". By default, new or revised content goes in `drafts/` so I
  can review it before promoting it into `notes/` myself.
- Never rewrite a whole file when a small addition or targeted edit will do —
  prefer appending a new section or editing one part.
- Before any multi-file change (e.g. "reorganize my notes"), describe the plan
  and wait for my go-ahead.

### Draft-first promotion workflow (strict)
- `drafts/` mirrors the folder structure of `notes/`, but should only ever
  hold that structure long-term — no leftover files. Files in `drafts/` are
  transient: they exist only while a change is in progress and are deleted
  once promoted, to avoid duplicating content that now lives in `notes/`.
- **Editing an existing note:** first copy the file from `notes/` into the
  same relative path in `drafts/`, then make the edits there. The original
  in `notes/` is left untouched until promotion.
- **Creating a new doc:** create it directly in `drafts/` at the same
  relative path it will eventually have in `notes/`.
- **Promotion (only when I say to update notes/ from drafts/):** go item by
  item (one file at a time) — show me the specific file/change, wait for my
  explicit approval, then apply it to `notes/` (create or overwrite as
  needed), and immediately delete that file from `drafts/` so only the
  folder structure remains there. Do not batch-apply multiple items on a
  single approval.

## Note format
- Each note starts with a one-line summary.
- Tag notes by UPSC GS paper where relevant: `#GS1` `#GS2` `#GS3` `#GS4`.
- Link related notes with `[[wikilink]]` style so they can be traced later.
- Beautify notes using Obsidian-rendered HTML/CSS, matching the style set in
  `notes/GS2/Social Justice.md`:
  - Section titles as a styled `<h2>`/`<h3>` banner (colored background, white
    text, padding, rounded corners) instead of plain `#`/`##` headings.
  - Summary/overview points wrapped in a styled HTML `<div>` (background
    color, left accent border, rounded corners, `<ul><li>` list inside)
    rather than a bare bullet list or an Obsidian-specific `> [!callout]` —
    callout syntax isn't guaranteed to render consistently, plain HTML is.
  - List items that pair a term with its explanation shown as colored
    "chip" divs (background color, left accent border, rounded corners),
    alternating between 2 accent colors.
  - Images placed in an HTML table alongside related text/lists so they sit
    side by side — do not mix Markdown syntax inside raw HTML blocks
    (Obsidian won't render it); use full HTML (`<img>`, `<ul><li>`, etc.)
    inside `<table>`/`<td>` blocks.
  - Keep colors thematically consistent with any source image/infographic
    being referenced, where applicable.

### Data-folder docs (`notes/data/`, `drafts/data/`)
- Files under a `data/` folder hold raw stats/figures only — style them as a
  data sheet, distinct from the prose-note style above, matching
  `notes/data/women.md`:
  - Same `<h2>` banner title as topic notes, but no callout-style overview box.
  - Group stats under uppercase "eyebrow" labels (category name, grey
    `#6b6b6b`, letter-spaced, ~1.1em, extra-bold/800 weight) instead of
    colored section banners.
  - Each stat is its own card (white background, colored top border by
    category, rounded corners): the indicator name (with year/period in
    muted text beside it) as the card title first, then the large bold
    number/figure below it, then a full-sentence summary explaining what
    the figure means underneath.
  - If the stat is a comparison (e.g. women vs. men), add a small table
    between the headline figure and the summary — one column per group
    (plus a "Gap" column if a % difference applies) — rather than folding
    the comparison into the headline number or a plain text line.
  - Cards stack one per row (`flex-direction:column`) — not a multi-column
    grid.
  - Topic notes in `notes/`/`drafts/` should link to the relevant data doc
    (`[[doc-name]]`) rather than duplicating the raw figures inline.

## Quotes
- Whenever a quote comes up (in conversation, a source, or a note I'm writing),
  ask if I want it added to `drafts/essay/quotes.md` (create it there first if
  it doesn't exist, per the draft-first workflow). Only add it if I say yes.
- Quotes are categorised by theme (e.g. Women) using the styling established in
  `notes/essay/quotes.md` — a category banner heading, then each quote as a
  colored chip with the quote text in italics and an attribution line.

## Daily current affairs
- New daily notes go in `daily/YYYY-MM-DD.md`.
- Periodically (when I ask), review recent daily notes and suggest which
  content should be merged into permanent topic notes in `notes/`.

## Memory
- For this project, store and retrieve persistent memory (feedback, project
  state, decisions worth remembering across sessions) in `.claude/memory/`
  inside this repo — **not** the global `~/.claude/projects/.../memory/`
  location. This keeps memory versioned and visible alongside the vault
  content itself.
- `.claude/memory/MEMORY.md` is the index; individual memory files sit
  alongside it, same format as the standard auto-memory system (frontmatter
  with `name`, `description`, `metadata.type`, linked via `[[name]]`).
- At the start of a session (or when memory seems relevant), read
  `.claude/memory/MEMORY.md` and follow up on relevant entries there, the
  same way you would with global auto-memory.
- When something is worth remembering (explicit "remember this", a
  correction, a validated approach, notable project state), write it into
  `.claude/memory/` following the same type conventions (user/feedback/
  project/reference) as global auto-memory, rather than the global location.

## Git
- After a study session, if I ask you to save progress, stage and commit
  with a short, descriptive message. Don't commit automatically otherwise.
