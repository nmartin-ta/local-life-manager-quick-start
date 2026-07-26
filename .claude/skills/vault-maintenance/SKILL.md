---
name: vault-maintenance
description: Use when the user asks to tidy, clean up, organize, or check the health of the vault — "tidy my vault", "clean up my vault", "anything out of place?", "vault maintenance". Finds orphans, missing links, misplaced files, and stale projects. Reports first; changes nothing without approval.
---

# Vault Maintenance

Housekeeping sweep over `my-obsidian-vault/`. **Always report first, act only on approval.** Never delete anything; clutter goes to `99 Archive/`.

## Sweep (read-only)

1. **Loose files**: notes sitting at the vault root (`my-obsidian-vault/`, where no loose .md files belong) or in the wrong folder for their `type`. Propose a PARA home for each: project-related → `01 Projects/<project folder>/` or link from the project's folder note; ongoing-topic → `02 Areas/`; source material → `03 References/`; inactive → `99 Archive/`.
2. **Orphans**: notes with no incoming or outgoing links. Skip the system notes: `98 Templates/`, `.claude/`, `02 Areas/Writing Voice.md`, and `02 Areas/Local Life Manager/`. Propose the most plausible links based on content.
3. **Missing metadata**: meeting notes without `date` or with an empty `related-to`; project notes without `status`.
4. **Stale projects**: `status: in-progress` projects whose folder note and linked meetings have no edits in ~60 days. Suggest `status: completed` plus a move to `99 Archive/`, or reviving.
5. **Broken links**: wikilinks pointing at notes that don't exist. Distinguish typos, where you propose the fix, from deliberate links to notes the user hasn't written yet, which you leave alone.
6. **Tasks**: in `05 Tasks/TaskNotes/`, flag open tasks with `due` before today (overdue) and open tasks with neither `due` nor `scheduled`; surface the unscheduled ones especially, since unscheduled work is what overwhelms people, not the total count. Suggest a date or `status: someday` for each, and never change a task's dates or status yourself.

## Report format

One short section per category with counts, the specific files, and the proposed action for each. End with: "Say which numbers to apply, or 'all'."

## Applying

Apply only what the user approved. Batch the edits, then summarize what changed in one line per file.
