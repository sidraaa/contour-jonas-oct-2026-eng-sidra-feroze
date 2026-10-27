# Software factory

This repo is a software factory. Tickets arrive as GitHub issues. The factory loop picks up each open issue, does the work, opens a pull request, and waits for manual review before closing the issue. We build and improve the loop. Features live in their own project folders.

## Progressive disclosure

This file is the index only. It stays under 100 lines. Read a project folder when that project is in scope, and skip the others. Links go one level deep: from this index to a project file, not through a chain of indexes.

When a project grows, add detail inside its folder. Update the row here. Do not paste that detail into this file.

## Rules

- One project, one folder.
- This file is the only index. Add, rename, or remove a project here in the same change as its folder.
- Keep this file under 100 lines.
- Training repo only: no Jonas or Contour product code, no real keys, tokens, or passwords in git.

## Index

| Project | Folder | What it is |
| --- | --- | --- |
| Factory loop | `.cursor/skills/factory-loop/` | Picks up GitHub issues: clarify, plan and approval, implement on a feature branch, browser verify, open a PR and wait for manual review, then label `answered` and close. Factual tickets skip build/PR. Guardrails: `.claude/settings.json`, `.cursor/cli.json`, `.cursor/permissions.json`, `.cursor/hooks.json`. See `SKILL.md`. |
| Skill doctor | `.claude/skills/skill-doctor/` | Finds failed traces in past agent transcripts, groups repeat failures by cause, and hardens the responsible skill with gates and checks. `prompt-audit` mode mirrors Claude's `/checkup prompt-audit` (stale paths, stale commands, contradictions, older-model patterns). See `SKILL.md`. |
| Prompt log | `.cursor/hooks/` | Stop hook `log-prompts.ps1` appends redacted prompts to `.cursor/prompts/<session>.jsonl`; that folder is committed, not gitignored. `commit-push.ps1` is best-effort: check `git log` for its commits before relying on it. |
| Retros | `retro/` | Dated factory retrospectives: human corrections, failed checks, friction, and audit findings grouped by cause, each with one proposed skill edit. |
| Todo | `todo/` | Client-side todo in IndexedDB: filters, due dates, tags, priority (filter + sort), daily recurrence (reset on complete), edit/delete series. Modules under `todo/lib/`; see `todo/IMPLEMENTATION.md`. Open `index.html` over HTTP. |
