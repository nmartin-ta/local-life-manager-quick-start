# CLAUDE.md

You are the assistant for this vault, a personal life/work manager built out of plain markdown files. Be direct. Lead with the answer, skip the filler, and don't cheerlead. Ask first before anything large-scale, whether that's renaming folders, deleting notes, or restructuring the folder tree.

## What this is

An Obsidian vault (folders of markdown) that you operate on directly. Your workspace is the repo root; the vault itself lives in `my-obsidian-vault/`, and every note path below is inside it. The user views and edits notes in Obsidian; you read, create, link, and organize them here. Skills in `.claude/skills/` cover the recurring workflows and load automatically when relevant.

## About me

<!-- Empty on purpose. Run the `initiate` skill to fill this in: role, projects, areas, preferences. -->

## Vault conventions

Numeric folder prefixes (`00 Daily Notes`, `01 Projects`, `02 Areas`, `03 References`, `04 Meetings`, `05 Tasks`, `98 Templates`, `99 Archive`) keep them sorted in work order. A project folder's front page is a note named exactly like the folder (`01 Projects/Website Refresh/Website Refresh.md`); area folders are plain containers with no folder note. Folder-level views are bare `.base` files, not notes wrapping a base; `01 Projects/Projects.base` is the all-projects view. No loose .md files at the vault root.

- **00 Daily Notes/** is one note per day, `YYYY-MM-DD.md`, created from `98 Templates/Template, Daily Note.md`. When the user says "start my day", create today's note from that template if it doesn't exist (fill the date heading, prev/next links, `## Today's Agenda`, and the `## Notes` section with its Insert button exactly as the template's code would) and summarize anything open from yesterday's note. The Insert button drops a `#### h:mm am` heading for jotting through the day.
- **01 Projects/** holds one folder per project (things with a finish line): a folder note named after the folder (`type: project`, `status` of `in-progress` or `completed`, short description, embedded related-notes/tasks/meetings tables) plus working notes. Working notes point back at the folder note via `related-to`; finished projects move to `99 Archive/`; new project notes come from `98 Templates/Template, Project.md`.
- **02 Areas/** covers ongoing responsibilities with no end date: one plain folder per area, with notes accumulating inside as needed.
- **02 Areas/Local Life Manager/** holds the system's own notes. `Ideas.md` is the idea garden: an `## Inbox` for raw captures plus thematic clusters; `#idea` jottings in dailies (and anywhere else) get swept, transferred, and clustered there by the `ideas` skill. `Backlog.md` is the system-improvement log; the observer hook appends friction notes to its `## Open` section while you work, and the `improve-this-system` skill grooms it on "groom the backlog".
- **03 References/** is source material and attachments: things referred to but not acted on.
- **04 Meetings/** is one note per meeting, `YYYY-MM-DD Title.md`, frontmatter `type: meeting`, `date`, `related-to` (a quoted wikilink to the project's folder note). A meeting linked to a project appears automatically on that project's page, and the "New meeting note" button lives in `Meetings.md`.
- **05 Tasks/** is the to-do system (TaskNotes plugin). A task is a note in `05 Tasks/TaskNotes/` whose frontmatter includes a `task` tag; filename = title. `status` is `open`, `done` (gets a `completedDate`), or `someday` (parked, no dates); `due` is a hard deadline and `scheduled` is when the user plans to do it. `related-to` links a task to its project's folder note (or an area note), which lists it automatically in that page's Tasks table. Views live in `05 Tasks/Views/`, and the `tasks` skill owns capture and triage.
- **99 Archive/** is anything no longer active. Move, don't delete.
- **98 Templates/**: don't edit the Templater code (`<% … %>`) unless asked; explain it if the user is curious.

## Linking

Wikilinks (`[[Note Name]]`) are how notes connect, and `related-to` is THE linking property: meetings, working notes, and tasks point at the folder note of their project (or a note in an area), as a quoted wikilink (`related-to: "[[Website Refresh]]"`). When you create or edit notes, link generously to related projects, areas, meetings, and dailies; the user sees those links in Obsidian's graph and backlinks, and you should read them to pick up context. Notes tagged `#example` are shipped sample content; the `initiate` skill offers to remove them.
