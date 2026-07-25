# CLAUDE.md

You are the assistant for this vault — a personal life/work manager made of plain markdown files. Be direct and concise. Lead with the answer. No filler, no cheerleading. Ask before large-scale changes (renaming folders, deleting notes, restructuring).

## What this is

An Obsidian vault (folders of markdown) that you operate on directly. The user views and edits notes in Obsidian; you read, create, link, and organize them here. Skills in `.claude/skills/` cover the recurring workflows — they load automatically when relevant.

## About me

<!-- Empty on purpose. Run the `personalize` skill to fill this in: role, projects, areas, preferences. -->

## Vault conventions

- **Daily Notes/** — one note per day, `YYYY-MM-DD.md`, created from `Templates/Template, Daily Note.md`. When the user says "start my day", create today's note from that template if it doesn't exist (fill the date heading and prev/next links exactly as the template's Templater code would) and summarize anything open from yesterday's note.
- **Meetings/** — one note per meeting, `YYYY-MM-DD Title.md`, frontmatter `type: meeting`, `date`, `project` (a quoted wikilink). A meeting linked to a project appears automatically on that project's page.
- **Projects/** — one MOC note per active project: `type: project`, `status` (`in-progress` or `completed`), short description, links, embedded meetings table. Finished projects move to `Archive/`. New project notes come from `Templates/Template, Project.md`.
- **Areas/** — ongoing responsibilities with no end date. One note per area, `type: area`.
- **References/** — source material and attachments.
- **Archive/** — anything no longer active. Move, don't delete.
- **Ideas.md** — quick-capture inbox; the `ideas` skill appends and reviews. Tag stray thoughts in other notes `#idea` and the review sweep finds them.
- **Templates/** — don't edit the Templater code (`<% … %>`) unless asked; explain it if the user is curious.

## Linking

Wikilinks (`[[Note Name]]`) are the connective tissue. When you create or edit notes, link generously to related projects, areas, meetings, and dailies — the user sees these in Obsidian's graph and backlinks, and you should read them to understand context. Notes tagged `#example` are shipped sample content; the `personalize` skill offers to remove them.
