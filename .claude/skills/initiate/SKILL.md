---
name: initiate
description: Use when a new user is getting started — "initiate", "get started", "set this up", "what is this?", "onboard me". Explains the system in stages, then personalizes the vault: About Me, real projects and areas, example cleanup.
---

# Initiate — Onboard a New User

Four stages, in order. Keep it conversational: short beats with real pauses, checking in ("ready?", "make sense?") between them instead of dumping everything at once. All note paths are inside `my-obsidian-vault/`.

## Stage 0 — Orient

Three beats, a checkpoint between each:

1. **It's all plain files.** Everything here is a markdown file in a folder. The user, Obsidian, and Claude all read the same folders, with no database in between and nothing locked to one app. Obsidian renders those files as a linked notebook, and Claude edits them in place.
2. **The tour.** One line per folder: `00 Daily Notes` (one note per day, the running log), `01 Projects` (one folder per thing with a finish line), `02 Areas` (ongoing responsibilities, no end date), `03 References` (source material you don't act on), `04 Meetings` (one dated note per meeting), `05 Tasks` (the to-do system), `98 Templates` (note templates), `99 Archive` (retired, never deleted). Then have them actually click things: the daily-note button in the left sidebar, the "New meeting note" button in `04 Meetings/Meetings.md`, a task view in `05 Tasks/Views/`, and the graph view.
3. **The complexity dial.** Obsidian can be as simple or as gnarly as you want. This vault sits in the middle: buttons, properties, bases, a bit of code inside the templates. Claude handles that layer. Whatever they want changed, they ask, and it gets set up.

## Stage 1 — Interview

One or two questions at a time, never a wall:

1. Name, role, and what the vault is mainly for (work, personal, both).
2. Their 2–5 active projects, with a one-line description and rough status each, mapping that status onto `in-progress` or `completed` (anything unfinished counts as `in-progress`).
3. Ongoing areas of responsibility, aiming for 2–5.
4. Working preferences worth remembering: brief vs. detailed answers, anything to always/never do.

## Stage 2 — Set up (confirm before writing)

1. **Fill `CLAUDE.md` → `## About me`**: replace the placeholder comment with name, role, what the vault is for, preferences. Under 15 lines.
2. **Seed `01 Projects/`**: for each project, create `01 Projects/<Name>/` with a folder note `<Name>.md`, named exactly like the folder, from `98 Templates/Template, Project.md`. Fill in the name, description, and status; copy the `base` blocks verbatim (they filter per-note automatically).
3. **Seed `02 Areas/`**: one plain folder per area, no folder note. Notes accumulate inside later.
4. **Offer to delete the example content.** List the files first, then delete only on confirmation. Nothing moves to Archive; this is shipped sample data:
   - `01 Projects/Website Refresh/` and `01 Projects/Policy Brief/` (both example projects)
   - `04 Meetings/2026-07-20 Website Refresh Kickoff.md`
   - the four example dailies in `00 Daily Notes/` (2026-07-20, 2026-07-21, 2026-07-25, 2026-07-26)
   - the four example tasks in `05 Tasks/TaskNotes/` (Draft sitemap, Review homepage copy, Choose site host, Plan next-quarter content calendar)
   - `02 Areas/Professional Development/Courses.md`
   - the `#example` lines in `02 Areas/Local Life Manager/Ideas.md` and `Backlog.md` (those two notes stay)

   `02 Areas/Admin/` is not example content; keep it. After deleting, also trim the sentence about `#example` notes from CLAUDE.md's Linking section, since it describes content that no longer exists.

## Stage 3 — Hand over

1. **Three habits**: open the daily note each morning (the button, or say "start my day"); press the New-meeting button for every meeting; jot `#idea` tags and task-like notes freely, since triage catches them.
2. **One demo prompt per skill**: "capture an idea: …" / "review my ideas" (ideas), "make a task: order a new laptop by Friday" / "triage my notes" (tasks), "tidy my vault" (vault-maintenance), "edit this email so it sounds like me" (voice), "make a skill that …" (improve-this-system).
3. **Invite complaints.** When something about the system annoys them, they should say so; the `improve-this-system` skill and the Backlog note in `02 Areas/Local Life Manager/` handle it from there.
