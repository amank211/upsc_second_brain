# Second Brain Starter — Setup

## 1. Place this folder
Move `second-brain-starter/` wherever you want your vault to live, and
rename it if you like (e.g. `upsc-notes/`).

## 2. Initialize git (do this first, before anything else)
Open a terminal in the folder and run:
```
git init
git add -A
git commit -m "baseline"
```
This gives you a permanent, recoverable history from day one.

## 3. Start Claude Code in the folder
```
cd path/to/your-vault
claude
```
Because of `.claude/settings.json`, every session starts in **plan mode** —
Claude will propose changes and wait for your approval before editing any
file. This is the main safety net; don't turn it off for this vault.

## 4. Feed it source material
```
> Read sources/some-article.pdf and create a note in drafts/ summarizing it,
  tagged by GS paper, linked to related notes in notes/ if any.
```
Review what lands in `drafts/`, then move approved notes into `notes/`
yourself (or explicitly tell Claude to do it).

## 5. Use the custom commands
- `/flashcards notes/some-note.md` — generate flashcards from a note
- `/quiz notes/some-note.md` — interactive quiz on a note
- `/review-daily` — scan the last week of daily/ notes and propose what to
  merge into permanent notes (as drafts, never direct edits)

## 6. If an edit goes wrong mid-session
Press **Esc twice** (or type `/rewind`) to open the checkpoint list and
restore files to before the bad edit. This only undoes Claude's own file
edits within the current session — it's a quick local undo, not a
replacement for git.

## 7. Save progress
At the end of a session:
```
> commit these changes with a short message
```
Git is the permanent record. Checkpoints and plan mode are there to stop
bad edits from happening in the first place.
