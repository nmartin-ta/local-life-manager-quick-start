# An Obsidian + Claude starter vault

Hi. I'm Nick. This repo is a small, working notes system: a folder of plain markdown files, an Obsidian configuration that turns them into a linked notebook, and a Claude configuration that lets an AI assistant read, file, and organize them for you. Clone it, open it, and you'll have the whole thing working in about fifteen minutes.

## The idea

Everything here is a plain text file in a folder. That's the load-bearing decision. Your notes aren't rows in someone's database or documents trapped inside an app. They're files you can open in any editor, back up however you like, and take with you when you leave. No app in this setup owns your data. If you stop using Obsidian tomorrow, or Claude, the files still work.

Three things read those same files. You, obviously. Obsidian, a free app that turns the folders into a linked, searchable notebook — every `[[Note Name]]` becomes a clickable connection, and the whole thing renders as a graph. And Claude, which operates on the files directly: it creates notes, files things into the right folders, adds links, drafts text, and tidies up after you. Same filing cabinet, two sets of hands.

Fair warning: this kit is a deliberately bare-bones seed of a much deeper system I use every day. Mine reads my calendar and email, preps my meetings, tracks project budgets, and writes my morning briefing before I sit down. None of that is in here, on purpose. The goal of this repo is a working start in fifteen minutes, and everything included earns its place at that size.

If you get hooked and want the deep end, come find me. I like talking about this stuff more than is probably healthy.

## Part 1: Set up Obsidian

1. **Install Obsidian** from [obsidian.md](https://obsidian.md). It's free. You need a reasonably current version (1.12.2 or newer), because the two bundled plugins require it. (Already have Obsidian? Update it first: Settings → General → Check for updates.)
2. **Get this repo onto your machine.** Either `git clone` it or use GitHub's "Download ZIP" button and unzip it somewhere sensible.
3. **Open it as a vault.** Launch Obsidian, choose "Open folder as vault," and pick the `my-obsidian-vault` folder inside the repo (the repo root holds Claude's configuration; the vault is the notes). A "vault" is just Obsidian's word for a folder of notes.
4. **Accept the trust prompt.** Obsidian will ask once whether to trust this vault's community plugins, because two come pre-installed. Say yes. **Templater** fills in dates and handles the small scripts inside the templates, and **Meta Bind** powers the "New meeting note" button. That's the extent of what they do here.

Now a quick tour. The folder layout is a simplified version of a method called PARA, and the core distinction is worth thirty seconds of your attention: **projects end, areas don't**. Two small conventions before the list: folder names start with numeric prefixes (`00`, `01`, …) so they stay sorted in the order you work them, and every project or area folder has a `+Name.md` note; the `+` marks it as that folder's front page.

- **00 Daily Notes/**: one note per day, your ongoing log.
- **01 Projects/**: one folder per project, meaning things with a finish line, like "Website Refresh" — a `+` front page plus working notes.
- **02 Areas/**: ongoing responsibilities that have no end date, like "Professional Development."
- **03 References/**: source material and attachments.
- **04 Meetings/**: one note per meeting, dated and linked to a project.
- **98 Templates/**: the note templates.
- **99 Archive/**: anything no longer active. Things move here instead of getting deleted.
- **Ideas.md**: a single quick-capture file for stray thoughts.

Five minutes of clicking will teach you more than I can in prose:

1. **Press the daily-note button**, the "Open today's daily note" icon in the left sidebar. Watch the template fire: today's note appears with the date as a heading and links to yesterday and tomorrow already in place. Inside, the "Insert Timestamp" button stamps the time as a small heading — jot under it through the day, and tag stray thoughts `#idea` for a later "review my ideas" pass.
2. **Open the example daily notes** (`2026-07-20` and `2026-07-21` in `00 Daily Notes/`) and click the links inside them. This is the habit that makes the whole system work: notes pointing at other notes.
3. **Open the graph view**, the icon that looks like connected dots. Sparse now. It won't stay that way.
4. **Open `04 Meetings/+Meetings.md`** and press the "New meeting note" button. It asks for a title, stamps today's date, files the new note into `04 Meetings/`, and adds a row to the table below, all in one go.
5. **Link that meeting to a project.** In your new meeting note, set the `related-to` property (in the Properties panel at the top of the note) to `[[+Website Refresh]]`. Now open the Website Refresh page in `01 Projects/`: your meeting is sitting in its meetings table. Nobody maintains that table. It builds itself from the links.

One more thing about Obsidian worth knowing early: there are thousands of community plugins, and anything that annoys you about the app, a plugin probably fixes. For years my task list lived in Todoist, a separate app with its own sync and its own inbox. Then I found TaskNotes, a plugin that turns the vault itself into a to-do app. Todoist went in the bin the same week. I left TaskNotes out of this kit to keep things simple, but it shows how far the plugin ecosystem goes.

One reassurance about the `<% %>` code in `98 Templates/`: it isn't yours to maintain. You never need to touch it, and Claude can explain or change any of it if you ask.

## Part 2: Set up Claude

Two options here. Pick whichever suits you:

1. **Claude Code**, which lives in your terminal. Install from [claude.com/claude-code](https://claude.com/claude-code), then launch `claude` inside the repo folder (the one containing `my-obsidian-vault`).
2. **Claude Desktop**, the app version. Download from [claude.com/download](https://claude.com/download) and open a session on the repo folder (Cowork mode works on a local directory).

Either way, Claude lands in the repo and immediately reads `CLAUDE.md`. That file is its orientation document: what this vault is, how the folders work, what the conventions are, and (once you fill it in) who you are. Think of it as the onboarding memo a new assistant reads on day one.

There's also a `.claude/skills/` folder holding five skills. A skill is a short instruction file for a recurring workflow; Claude loads the right one automatically when your request matches. You never invoke them by name. You just say the thing. And like everything else here, the skills are plain markdown: open the folder and read them, each one fits on a page.

**Your first move: say "personalize this vault."** Claude will interview you (name, role, your two-to-five active projects, your ongoing areas, how you like your answers), a question or two at a time, nothing painful. Then it fills in the About Me section of `CLAUDE.md`, creates a project page for each real project, creates your area notes, and offers to delete the example content: everything tagged `#example`, which covers the Website Refresh project, the Professional Development area, the kickoff meeting, the three sample dailies, and one line in `Ideas.md`. Ten minutes, and the vault is yours instead of mine.

After that, try these:

| Say this | What happens |
|---|---|
| "start my day" | Creates today's daily note and summarizes anything left open from yesterday. (This one's a convention in CLAUDE.md rather than a skill. Same effect.) |
| "capture an idea: …" | Appends a dated bullet to `Ideas.md`. Capture only; no over-eager elaboration. |
| "review my ideas" | Later, when ideas have piled up: clusters them and proposes which should become projects, which get filed, which get dropped. |
| "tidy my vault" | Sweeps for orphaned notes, missing links, stale projects, misplaced files. Reports first; changes nothing without your approval. |
| "edit this email so it sounds like me" | Drafts or edits in your voice, using a style memory it builds over time at `02 Areas/Writing Voice.md`. Also strips the usual AI tells. |
| "make a skill that …" | Writes a new skill file for any workflow you find yourself repeating. More on this below. |

One concept ties Obsidian and Claude together: **the wikilinks you make aren't decoration.** When Claude opens a meeting note and sees `related-to: "[[+Website Refresh]]"`, it follows that link and reads the project page. When your daily note links to a meeting and the meeting links back to a project, Claude can trace your whole week without asking you anything. A well-linked vault literally makes Claude understand your world better. Every link you add is context you never have to explain again.

## Part 3: Leveling up

Where this goes once the basics feel boring:

**Integrations.** Connect Claude to your calendar and email (Microsoft 365, Google, and others have connectors) and the workflows start compounding. My morning-briefing skill reads my inbox and calendar, cross-references my project notes, and writes the day's priorities into my daily note before I sit down. All of that is built on the same seed you're holding right now, plus a couple of connectors and one extra skill.

**More plugins.** TaskNotes, as mentioned. Deeper Templater use, once you're comfortable reading the template code. And whatever else you find when you go browsing the plugin directory on a slow afternoon.

**Schedules.** Briefings that happen on a timer, unprompted.

**Growing the system itself.** This is the real endgame, and it's why the `improve-this-system` skill exists. Any workflow you notice yourself repeating ("every Friday I summarize the week," "after each meeting I extract the action items") can become a skill: say "make a skill that does X" and Claude writes the skill file for you. The system you have a year from now won't be this kit. It'll be the thing you and Claude grew out of it, one workflow at a time.

That's the pitch. Files you own, an app that makes them navigable, an assistant that does the filing. If you build something interesting on top of it, or get stuck, come talk to me.

---

MIT licensed. See [LICENSE](LICENSE).
