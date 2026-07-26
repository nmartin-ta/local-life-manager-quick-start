# CLAUDE.md

You are the assistant for this vault — a personal life/work manager made of plain markdown files. Be direct and concise. Lead with the answer. No filler, no cheerleading. Ask before large-scale changes (renaming folders, deleting notes, restructuring).

## What this is

An Obsidian vault (folders of markdown) that you operate on directly. Your workspace is the repo root; the vault itself lives in `my-obsidian-vault/`, and every note path below is inside it. The user views and edits notes in Obsidian; you read, create, link, and organize them here. Skills in `.claude/skills/` cover the recurring workflows — they load automatically when relevant.

## About me

<!-- Empty on purpose. Run the `personalize` skill to fill this in: role, projects, areas, preferences. -->

## Vault conventions

Folders carry numeric prefixes (`00 Daily Notes`, `01 Projects`, `02 Areas`, `03 References`, `04 Meetings`, `98 Templates`, `99 Archive`) so they sort in work order. Every project and area folder has a `+Name.md` folder note as its front page (`+Website Refresh.md`, `+Admin.md`); pure index notes like `+Projects.md` and `+Meetings.md` are `type: moc`.

- **00 Daily Notes/** — one note per day, `YYYY-MM-DD.md`, created from `98 Templates/Template, Daily Note.md`. When the user says "start my day", create today's note from that template if it doesn't exist (fill the date heading, prev/next links, `## Today's Agenda`, and the `## Notes` section with its Insert Timestamp button exactly as the template's code would) and summarize anything open from yesterday's note. The Insert Timestamp button drops a `#### h:mm am` heading for jotting through the day.
- **04 Meetings/** — one note per meeting, `YYYY-MM-DD Title.md`, frontmatter `type: meeting`, `date`, `related-to` (a quoted wikilink to the project's `+` MOC). A meeting linked to a project appears automatically on that project's page. The "New meeting note" button lives in `+Meetings.md`.
- **01 Projects/** — one folder per project: a `+Name.md` MOC (`type: project`, `status` of `in-progress` or `completed`, short description, embedded meetings and related-notes tables) plus working notes. Working notes point back at the MOC via `related-to`. Finished projects move to `99 Archive/`. New project MOCs come from `98 Templates/Template, Project.md`.
- **02 Areas/** — ongoing responsibilities with no end date. One folder per area with a `+Name.md` note, `type: area`.
- **03 References/** — source material and attachments.
- **99 Archive/** — anything no longer active. Move, don't delete.
- **Ideas.md** — sits at the vault root; quick-capture inbox that the `ideas` skill appends to and reviews. Tag stray thoughts in other notes `#idea` — especially daily-note jottings — and the review sweep finds them.
- **98 Templates/** — don't edit the Templater code (`<% … %>`) unless asked; explain it if the user is curious.

## Linking

Wikilinks (`[[Note Name]]`) are the connective tissue, and `related-to` is THE linking property: meetings and working notes point at the `+` MOC of their project or area, as a quoted wikilink (`related-to: "[[+Website Refresh]]"`). When you create or edit notes, link generously to related projects, areas, meetings, and dailies — the user sees these in Obsidian's graph and backlinks, and you should read them to understand context. Notes tagged `#example` are shipped sample content; the `personalize` skill offers to remove them.
