# An Obsidian + Claude starter vault

Hi. I'm Nick. This repo is a small, working notes system: a folder of plain markdown files, an Obsidian configuration that turns them into a linked notebook, and a Claude configuration that lets an AI assistant read, file, and organize them for you. Clone it, open it, and you'll have the whole thing working in about fifteen minutes.

## The idea

Everything here is a plain text file in a folder. That's the load-bearing decision. Your notes aren't rows in someone's database or documents trapped inside an app. They're files you can open in any editor, back up however you like, and take with you when you leave. No app in this setup owns your data. If you stop using Obsidian tomorrow, or Claude, the files still work.

Three things read those same files. You, obviously. Obsidian, a free app that turns the folders into a linked, searchable notebook — every `[[Note Name]]` becomes a clickable connection, and the whole thing renders as a graph. And Claude, which operates on the files directly: it creates notes, files things into the right folders, adds links, drafts text, and tidies up after you. Same filing cabinet, two sets of hands.

A word on complexity. Obsidian can be as simple or as complicated as you want: some people keep a flat folder of text files, some build things that look like mission control. This kit sits in the middle, with buttons, properties, automatic tables, and a little template code. That middle layer is exactly what Claude is good at. You never have to learn it. Changing any of it is a matter of asking, not learning to code.

Fair warning: this kit is a deliberately bare-bones seed of a much deeper system I use every day. Mine reads my calendar and email, preps my meetings, tracks project budgets, and writes my morning briefing before I sit down. None of that is in here, on purpose. The goal of this repo is a working start in fifteen minutes, and everything included earns its place at that size.

If you get hooked and want the deep end, come find me. I like talking about this stuff more than is probably healthy.

## Setup

1. **Get this repo onto your machine.** Either `git clone` it or use GitHub's "Download ZIP" button and unzip it somewhere sensible.
2. **Open the vault in Obsidian.** Install Obsidian from [obsidian.md](https://obsidian.md) (it's free; you need 1.12.2 or newer). Choose "Open folder as vault" and pick the `my-obsidian-vault` folder inside the repo. Obsidian will ask once whether to trust the vault's community plugins; say yes. There are three: **Templater** fills in dates and handles the small scripts inside the templates, **Meta Bind** powers the "New meeting note" button, and **TaskNotes** turns the notes in `05 Tasks/` into a to-do system.
3. **Point Claude at the repo folder**, the one containing `my-obsidian-vault`, not the vault itself: Claude's configuration lives at the root. Either [Claude Code](https://claude.com/claude-code) in your terminal (launch `claude` inside the repo) or [Claude Desktop](https://claude.com/download) with a Cowork session on the repo directory.
4. **Say "initiate."** Claude takes it from there: a short guided tour of the folders (you'll press the buttons, open a task view, see the graph), then an interview about your actual projects and areas, then it rebuilds the vault around your life and offers to clear out the example content. Ten minutes, and the vault is yours instead of mine.

When Claude lands in the repo it reads `CLAUDE.md` first. That file is its orientation document: what this vault is, how the folders work, what the conventions are, and (once initiate fills it in) who you are. Think of it as the onboarding memo a new assistant reads on day one.

There's also a `.claude/skills/` folder holding six skills. A skill is a short instruction file for a recurring workflow; Claude loads the right one automatically when your request matches. You never invoke them by name. You just say the thing. And like everything else here, the skills are plain markdown: open the folder and read them, each one fits on a page.

After initiate, try these:

| Say this | What happens |
|---|---|
| "start my day" | Creates today's daily note and summarizes anything left open from yesterday. (This one's a convention in CLAUDE.md rather than a skill. Same effect.) |
| "capture an idea: …" | Appends a dated bullet to the idea garden in `02 Areas/Local Life Manager/Ideas.md`. Capture only; no over-eager elaboration. |
| "review my ideas" | Later, when ideas have piled up: sweeps your `#idea` jottings into the garden, clusters them, and proposes which should become projects, which get filed, which get dropped. |
| "make a task: order new laptop by Friday" | Creates a task note in `05 Tasks/TaskNotes/` — after checking it isn't already there. "By Friday" becomes the due date. |
| "triage my notes" | Sweeps recent dailies and meeting action items for commitments that never became tasks, and proposes them as a numbered list. |
| "tidy my vault" | Sweeps for orphaned notes, missing links, stale projects, misplaced files. Reports first; changes nothing without your approval. |
| "edit this email so it sounds like me" | Drafts or edits in your voice, using a style memory it builds over time at `02 Areas/Writing Voice.md`. Also strips the usual AI tells. |
| "make a skill that …" | Writes a new skill file for any workflow you find yourself repeating. More on this below. |

One concept ties Obsidian and Claude together: **the wikilinks you make aren't decoration.** When Claude opens a meeting note and sees `related-to: "[[Website Refresh]]"`, it follows that link and reads the project page. When your daily note links to a meeting and the meeting links back to a project, Claude can trace your whole week without asking you anything. A well-linked vault literally makes Claude understand your world better. Every link you add is context you never have to explain again.

## Leveling up

Where this goes once the basics feel boring:

**Integrations.** Connect Claude to your calendar and email (Microsoft 365, Google, and others have connectors) and the workflows start compounding. My morning-briefing skill reads my inbox and calendar, cross-references my project notes, and writes the day's priorities into my daily note before I sit down. All of that is built on the same seed you're holding right now, plus a couple of connectors and one extra skill.

**More plugins.** There are thousands of community plugins, and anything that annoys you about Obsidian, a plugin probably fixes. TaskNotes, which powers `05 Tasks/`, is the proof. For years my task list lived in Todoist, a separate app with its own sync and its own inbox. Then I found a plugin that turns the vault itself into a to-do app; Todoist went in the bin the same week, and TaskNotes ships in this kit. Deeper Templater use belongs here too, once you're comfortable reading the template code.

**Schedules.** Briefings that happen on a timer, unprompted. A periodic "tidy my vault" audit is a good first one: the system stays healthy without you thinking about it.

**Version control.** The vault is just files, so git works on it. Commit now and then (or ask Claude to) and you get free, forever undo: every note's history, visible diffs when Claude changes things, and a painless way to sync between machines. If you cloned this repo you're already standing in a git repository; make it your own and start committing.

**Growing the system itself.** This is the real endgame, and it's why the `improve-this-system` skill exists. Any workflow you notice yourself repeating ("every Friday I summarize the week," "after each meeting I extract the action items") can become a skill: say "make a skill that does X" and Claude writes the skill file for you. Claude also keeps a quiet list of friction it notices in `02 Areas/Local Life Manager/Backlog.md`; say "groom the backlog" occasionally and decide what's worth fixing. The system you have a year from now won't be this kit. It'll be the thing you and Claude grew out of it, one workflow at a time.

That's the pitch. Files you own, an app that makes them navigable, an assistant that does the filing. If you build something interesting on top of it, or get stuck, come talk to me.

---

MIT licensed. See [LICENSE](LICENSE).
