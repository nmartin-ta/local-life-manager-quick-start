---
name: personalize
description: Use when a new user wants to make this vault theirs — first-run setup, "personalize", "set up my vault", "get started", "make this mine". Interviews the user, fills in CLAUDE.md About Me, seeds Projects and Areas, offers to clear example content.
---

# Personalize This Vault

First-run onboarding. Interview the user, then set up the vault around their real life. Ask questions **one or two at a time**, not as a wall. All note paths are inside `my-obsidian-vault/`.

## Interview

1. Name, role, and what they mainly want this vault for (work, personal, both).
2. Their 2–5 active projects — things with an end state. For each: one-line description and rough status.
3. Their ongoing areas of responsibility (no end date) — aim for 2–5.
4. Working preferences worth remembering: how they like answers (brief vs. detailed), anything they want you to always/never do.

## Actions (after the interview, confirm before writing)

1. **Fill `CLAUDE.md` → `## About me`**: replace the placeholder comment with a compact summary — name, role, what the vault is for, preferences. Keep it under 15 lines.
2. **Seed `01 Projects/`**: one folder per project — `01 Projects/<Name>/` containing a `+<Name>.md` MOC created from `98 Templates/Template, Project.md` (fill in the name, description, and status; the `base` blocks must be copied verbatim — they filter per-note automatically). Map the interview's rough status onto `status: in-progress` or `status: completed` (anything not finished is `in-progress`).
3. **Seed `02 Areas/`**: one folder per area — `02 Areas/<Name>/` containing a `+<Name>.md` note with frontmatter `type: area`, a short description, and a `## Notes` section.
4. **Offer to delete example content**: everything tagged `#example` — the `01 Projects/Website Refresh/` folder (including Design Parameters and User Journey), the `02 Areas/Professional Development/` folder, the kickoff meeting note, the three example dailies, the four example tasks in `05 Tasks/TaskNotes/` (Draft sitemap, Review homepage copy, Choose site host, Plan next-quarter content calendar), and the Ideas.md example line. `02 Areas/Admin/` is not example content — keep it. List the files first; delete only on confirmation — move nothing to Archive, these are samples not user data. After deleting, also remove the sentence about `#example` notes from CLAUDE.md's Linking section (it describes content that no longer exists).

## Wrap up

Tell the user what changed, then suggest three first habits: press the daily-note button each morning (or say "start my day"), use the New Meeting button in `04 Meetings/+Meetings.md`, and say "capture an idea: …" when something occurs to them.
