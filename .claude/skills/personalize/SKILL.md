---
name: personalize
description: Use when a new user wants to make this vault theirs — first-run setup, "personalize", "set up my vault", "get started", "make this mine". Interviews the user, fills in CLAUDE.md About Me, seeds Projects and Areas, offers to clear example content.
---

# Personalize This Vault

First-run onboarding. Interview the user, then set up the vault around their real life. Ask questions **one or two at a time**, not as a wall.

## Interview

1. Name, role, and what they mainly want this vault for (work, personal, both).
2. Their 2–5 active projects — things with an end state. For each: one-line description and rough status.
3. Their ongoing areas of responsibility (no end date) — aim for 2–5.
4. Working preferences worth remembering: how they like answers (brief vs. detailed), anything they want you to always/never do.

## Actions (after the interview, confirm before writing)

1. **Fill `CLAUDE.md` → `## About me`**: replace the placeholder comment with a compact summary — name, role, what the vault is for, preferences. Keep it under 15 lines.
2. **Seed `Projects/`**: one MOC note per project, copying the exact structure of `Projects/Website Refresh.md` (frontmatter `type: project` + `status`, description line, `## Related notes`, `## Meetings` with the same embedded `base` block — copy the base block verbatim, it filters per-note automatically).
3. **Seed `Areas/`**: one note per area, structure of `Areas/Professional Development.md` (frontmatter `type: area`, short description, `## Notes`).
4. **Offer to delete example content**: everything tagged `#example` (example project, area, meeting, two daily notes, the Ideas.md example line). List the files first; delete only on confirmation — move nothing to Archive, these are samples not user data.

## Wrap up

Tell the user what changed, then suggest three first habits: press the daily-note button each morning (or say "start my day"), use the New Meeting button in `Meetings/Meetings.md`, and say "capture an idea: …" when something occurs to them.
