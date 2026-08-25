---
name: reference-github-repo
description: This vault is pushed to a public GitHub repo; gh CLI is installed but not on PATH
metadata:
  type: reference
---

The vault (`C:\Users\amank\upsc_second_brain`) is a git repo pushed to **https://github.com/amank211/upsc_second_brain**, set to **public** visibility (explicit user choice — was briefly private, user asked to switch to public). Remote `origin` is already configured; `git push` / `git pull` work directly.

**GitHub CLI (`gh`) is installed but not on PATH** in this environment. Invoke it with the full path: `C:\Program Files\GitHub CLI\gh.exe`. Authenticated as GitHub user `amank211`.

`.obsidian/` (Obsidian editor config) and `temp/` (raw scratch source PDFs) are intentionally left untracked/uncommitted — do not `git add` them without asking first; this has been the consistent pattern across every commit in this vault.

**How to apply:** When the user asks to "push", "save to GitHub", or similar, use `git push` directly (remote already exists — no need to recreate it). Only reach for `gh.exe` (with the full path) for GitHub-specific operations (repo settings, visibility changes, PRs, issues) that plain `git` can't do.
