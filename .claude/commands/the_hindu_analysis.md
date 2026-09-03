Analyse today's The Hindu newspaper for UPSC preparation.

## Step 1 — Locate today's PDF

Today's date is available via the system. Look in `sources/newspapers/the_hindu/` for a PDF whose filename contains today's date (files follow a pattern like `th.*YYYY_MM_DD*.pdf` — pick the one whose embedded date matches today). If multiple files exist, process all of them. If none is found, report that clearly and stop.

## Step 2 — Read the PDF

Read the PDF using the Read tool **without** a `pages` parameter (pdftoppm is not installed; the tool renders pages as text). For PDFs longer than 20 pages, read in batches of 20 pages at a time, accumulating the full text before proceeding. Record the **page number and section name** (e.g. "Page 1 — Front Page", "Page 4 — News", "Page 8 — Editorial") for every article as you go, so you can attribute each article to its correct newspaper section.

## Step 3 — Extract articles in newspaper page order

Identify distinct articles by detecting bold or ALL-CAPS headlines followed by body text, section/page breaks, bylines, and topic changes between adjacent blocks.

**CRITICAL — Sections to cover (never skip any article in these):**
Front Page, States, Science, Editorial, Opinion, Text & Context, Business, World

For articles in any of the sections above: do **not** apply the UPSC-relevance skip. Write a card for every article, even if UPSC relevance seems low. The "skip entirely" rule below applies only to layout elements — never to editorial content within those sections.

**Skip entirely (layout elements only):** stock tables, weather boxes, sports scorecards, classified ads, TV listings, and any text block under 80 words with no clear headline.

Build an ordered list that follows **newspaper page order** — exactly as the articles appear page by page:

```
[N] Headline — Page X (Section Name)
```

Example sections and their typical page range in The Hindu International Edition:
- **Front Page** (p.1)
- **News / National** (p.4–6 typically)
- **States** (p.2–3 typically)
- **The World** (p.14–15 typically)
- **Business & Economy** (p.12–13 typically)
- **Science / Text & Context** (p.7, p.10 typically)
- **Editorial / Opinion** (p.8–9 typically)

The actual section names are printed on the page — use those. Do **not** reorder articles by GS topic.

## Step 4 — Classify and analyse each article

**CRITICAL — one article at a time:** Write and append each article's card to the output file immediately after completing it, then proceed to the next article. Do **not** batch multiple articles into a single write. Do **not** draft all cards first and write at the end. The workflow is strictly:

> write article N card → append to file → proceed to article N+1

This ensures the file builds incrementally and no work is lost if the session is interrupted.

**Before classifying**, load the relevant syllabus files as reference:
- `sources/syllabus/mains/GS1.md`, `GS2.md`, `GS3.md`, `GS4.md`
- `sources/syllabus/prelims/paper1.md`, `paper2.md`

**CRITICAL — verify before writing:** Any factual claim you add beyond what the PDF explicitly states — role titles, positions held, statistics, act names, year of enactment, body composition, historical precedents — **must be verified via internet search before being written into the card.** This applies especially to:
- Current political positions (CM, LoP, minister, party office-bearer)
- Recent appointments and leadership changes
- Current data figures and rankings
- Status of ongoing schemes, cases, or negotiations

Use the WebSearch tool to confirm the current facts before writing. Do not rely solely on training-data knowledge for time-sensitive details, as it may be outdated.

For each article produce a three-section card:

---

### Section A — Summary (prose paragraph, not bullets)

Write a **single prose paragraph of 100–200 words**. Cover: what happened, who is involved, where, and why it matters for UPSC. Do not use bullet points. Do not pad — write tightly.

---

### Section B — UPSC Mains Classification

Use this exact notation:

```
GS Paper [N] → [Broad Category] → [Specific sub-topics, comma-separated]
```

Examples:
- `GS Paper II → International Relations → India-China bilateral relations; management of the Line of Actual Control`
- `GS Paper II → Indian Polity → Constitutional amendments; Parliament; electoral reforms`
- `GS Paper III → Agriculture → Food security; export policy; minimum support price`

List all genuinely applicable papers (one line each). Do **not** note a "likely question angle" — the notation is enough.

---

### Section C — Background Knowledge (5 detailed bullets)

Exactly **5 bullet points**, each with a **bold term** followed by a full explanatory sentence. Include constitutional articles, act names with year, key bodies and their mandate, historical precedents, data points, and policy context. Never write one-liners — each bullet should be 2–4 sentences where needed to give a complete picture.

Format:
```
- **Term or Concept (year if applicable):** Full sentence explaining what it is, its statutory basis, composition, mandate, or significance. Include follow-on detail if it adds UPSC value.
```

Examples:
- **Special Representatives Mechanism (2003):** Established under the India-China Joint Declaration to resolve the boundary dispute at a political level. It operates alongside military-level talks (Border Personnel Meetings) and is guided by the 2005 Agreement on Political Parameters and Guiding Principles. The current Indian Special Representative is the NSA.
- **APMC Act and state amendments:** The Agricultural Produce Market Committee Act governs wholesale trade of farm produce through regulated mandis. Several states have amended it to allow direct farmer-to-buyer sales outside mandis, a precursor reform to the now-repealed Farm Laws of 2020.

---

### Topic tags — per article

Every article gets inline topic tags. Use the three color schemes below and pick 2–4 tags per article from the list:

**Tag color schemes:**
- Blue (`background:#E8EEF6; color:#2858A0`) — International Relations, Diplomacy, Foreign Policy, Security, Defence
- Red-orange (`background:#FFF0E6; color:#B84020`) — Polity, Governance, Elections, Federalism, Labour, Social Justice, Health, Education, Women, Environment
- Green (`background:#E8F2E8; color:#1A5C2A`) — Economy, Agriculture, Infrastructure, Trade, Banking, Industry
- Purple (`background:#F0EBF6; color:#5B2C8D`) — Science & Technology, Space, AI, Data, Privacy

Tag HTML:
```html
<span style="background:#E8EEF6;color:#2858A0;font-size:0.72em;font-weight:700;padding:2px 9px;border-radius:3px;margin-right:4px;">International Relations</span>
```

---

If an article has **zero** UPSC relevance AND is **not** in one of the eight mandatory sections listed in Step 3, skip it — do not produce a card.

## Step 5 — Save as a Markdown file

After processing all articles, write the output to:

```
current_affairs/the_hindu/YYYY-MM-DD.md
```

Create the folder path if it does not exist. This is a new `current_affairs/` tree, not `notes/` or `drafts/`, so the draft-first rule does not apply — write directly.

**File structure:**

```
---
date: YYYY-MM-DD
source: The Hindu (International Edition)
articles: N
tags: [current-affairs, GS2, GS3, ...]
---

<!-- one-line summary of the day's most important story -->

<!-- Section divider for each newspaper section -->
<!-- Then article cards in page order -->
```

**Section divider** — insert before the first article of each new newspaper section:

```html
<p style="font-size:0.68em;letter-spacing:0.12em;text-transform:uppercase;color:#8A8278;font-weight:700;margin:32px 0 4px 0;">▌ Front Page</p>
```

**Article card structure** (one per article, in page order):

```html
<!-- Article header: headline + topic tags -->
<h2 style="background:#1E2D3D;color:#fff;padding:12px 18px;border-radius:7px 7px 0 0;margin:28px 0 0 0;font-size:1.05em;">
  Headline Text Here
</h2>
<p style="margin:0 0 6px 0;padding:4px 18px 6px 18px;background:#f4f6f8;border-radius:0 0 5px 5px;font-size:0.82em;">
  [TOPIC TAGS HERE]
  <span style="color:#8A8278;font-size:0.9em;margin-left:8px;">Page N · Section Name</span>
</p>

<!-- UPSC Classification (plain Markdown list, not styled chips) -->
**UPSC Mains Classification**
- GS Paper II → International Relations → India-China bilateral; LAC management

<!-- Summary -->
**Summary**
<div style="background:#EDF4F2;border-left:4px solid #4A8A78;border-radius:0 5px 5px 0;padding:12px 16px;margin:10px 0 6px 0;">
[Prose paragraph here — 100–200 words, no bullet points]
</div>

<!-- Background Knowledge -->
**Background Knowledge**
<div style="background:#F9F3E8;border-left:4px solid #B07030;border-radius:0 5px 5px 0;padding:12px 16px;margin:6px 0 16px 0;">
<ul>
<li><strong>Term (year):</strong> Full explanatory sentence(s).</li>
<li><strong>Term:</strong> Full explanatory sentence(s).</li>
<li><strong>Term:</strong> Full explanatory sentence(s).</li>
<li><strong>Term:</strong> Full explanatory sentence(s).</li>
<li><strong>Term:</strong> Full explanatory sentence(s).</li>
</ul>
</div>
```

**Header banner color** — use the same dark navy `#1E2D3D` for all cards (consistent, not varied by GS topic). The topic tags on each card provide the color differentiation.

**Do NOT** group articles by GS topic. Maintain strict newspaper page order throughout.

## Step 6 — Offer to publish as an HTML Artifact

After saving the Markdown file, ask:
> "Want me to also publish this as an HTML Artifact for easy browser reading?"

Only publish if the user says yes.

## Step 7 — Offer to save to daily note

Also ask:
> "Want me to append a brief summary to today's daily note (`daily/YYYY-MM-DD.md`)?"

Only create or append to the daily note if the user says yes. If the daily file is fresh, create it directly in `daily/`. If it already has reviewed content, follow the draft-first rule from CLAUDE.md.
