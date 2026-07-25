---
name: vault-maintenance
description: Use when the user asks to tidy, clean up, organize, or check the health of the vault — "tidy my vault", "clean up my vault", "anything out of place?", "vault maintenance". Finds orphans, missing links, misplaced files, and stale projects. Reports first; changes nothing without approval.
---

# Vault Maintenance

Housekeeping sweep. **Always report first, act only on approval.** Never delete — the fix for clutter is `Archive/`, not removal.

## Sweep (read-only)

1. **Loose files**: notes sitting at the vault root (besides `Ideas.md`, `README.md`, `CLAUDE.md`) or in the wrong folder for their `type`. Propose a PARA home for each: project-related → `Projects/` or link from the project MOC; ongoing-topic → `Areas/`; source material → `References/`; inactive → `Archive/`.
2. **Orphans**: notes with no incoming or outgoing links (skip `Templates/`, `.claude/`, and `Areas/Writing Voice.md`). Propose the most plausible links based on content.
3. **Missing metadata**: meeting notes without `date` or with an empty `project`; project notes without `status`.
4. **Stale projects**: `status: in-progress` projects whose MOC and linked meetings have no edits in ~60 days. Suggest marking `status: completed` and moving to `Archive/`, or reviving.
5. **Broken links**: wikilinks pointing at notes that don't exist. Distinguish typos (propose the fix) from intentional future notes (leave alone).

## Report format

One short section per category with counts, the specific files, and the proposed action for each. End with: "Say which numbers to apply, or 'all'."

## Applying

Apply only what the user approved. Batch the edits, then summarize what changed in one line per file.
