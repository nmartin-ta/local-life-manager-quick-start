# An Obsidian + Claude starter vault

Hi, I'm Nick. This is a small notes system you can clone and run: a folder of markdown files, plus the Obsidian and Claude configuration that makes them useful. Setup takes about fifteen minutes.

## The idea

Everything here is a plain text file in a folder. Your notes aren't rows in somebody's database or documents locked inside an app. They're files, so you can open them in any editor, back them up however you like, and still read them in ten years if both of the tools below have gone out of business.

Three things read those same files. You, obviously. Obsidian, a free app that turns the folders into a linked, searchable notebook, where every `[[Note Name]]` becomes a clickable connection and you can see the whole web of them at once. And Claude, which works on the files directly: making notes, filing them where they belong, adding links, drafting text, cleaning up after you.

Obsidian can be as simple or as complicated as you want. Some people keep a flat folder of text files and never touch a setting; other people build the kind of thing that looks like mission control and has a plugin for everything. This kit sits in the middle, with buttons, note properties, tables that fill themselves in, and a bit of code inside the templates. That middle layer is the part Claude is good at, so you don't have to learn it to change it. When you want something to work differently, ask, and it gets set up.

What's here is a stripped-down version of a system I use every day. Mine reads my calendar and email, preps my meetings, tracks project budgets, and writes a briefing into my daily note before I sit down in the morning. None of that is in this repo. Fifteen minutes to something working was the constraint I set, and most of my system doesn't fit inside it.

If you want the deep end, come find me.

## Setup

1. **Get this repo onto your machine.** Either `git clone` it or use GitHub's "Download ZIP" button and unzip it somewhere sensible.
2. **Open the vault in Obsidian.** Install Obsidian from [obsidian.md](https://obsidian.md) — it's free, and you need version 1.12.2 or newer. Choose "Open folder as vault" and pick the `my-obsidian-vault` folder inside the repo. Obsidian will ask once whether you trust the vault's community plugins; say yes. There are three of them. **Templater** fills in dates and runs the small scripts inside the templates, **Meta Bind** powers the buttons, and **TaskNotes** turns the notes in `05 Tasks/` into a to-do system.
3. **Point Claude at the repo folder** — the one containing `my-obsidian-vault`, not the vault itself, because Claude's configuration lives at the root. Use either [Claude Code](https://claude.com/claude-code) in your terminal (launch `claude` inside the repo) or [Claude Desktop](https://claude.com/download) with a Cowork session on the repo directory.
4. **Say "initiate."** Claude takes it from there: a short tour of the folders where you press the buttons and open a task view yourself, then some questions about your actual projects and areas, then it rebuilds the vault around your life and offers to clear out my example content.

When Claude lands in the repo it reads `CLAUDE.md` first. That file explains what the vault is, how the folders work, which conventions to follow, and, once initiate has filled it in, who you are.

There's also a `.claude/skills/` folder holding six skills. A skill is a short instruction file for a workflow you repeat; Claude loads the right one when your request matches, so you don't call them by name. They're plain markdown, so read any of them if you're curious what it actually does.

After initiate, try these:

| Say this | What happens |
|---|---|
| "start my day" | Creates today's daily note and summarizes anything left open from yesterday. (A convention in CLAUDE.md rather than a skill, but it works the same.) |
| "capture an idea: …" | Appends a dated bullet to the idea garden in `02 Areas/Local Life Manager/Ideas.md`, then stops there. |
| "review my ideas" | Later, once ideas have piled up: sweeps your `#idea` jottings into the garden, groups them, and proposes which should become projects, which get filed, and which get dropped. |
| "make a task: order new laptop by Friday" | Creates a task note in `05 Tasks/TaskNotes/`, after checking it isn't already there. "By Friday" becomes the due date. |
| "triage my notes" | Sweeps recent dailies and meeting action items for commitments that never became tasks, and proposes them as a numbered list. |
| "tidy my vault" | Looks for orphaned notes, missing links, stale projects, misplaced files. Reports first and changes nothing without your say-so. |
| "edit this email so it sounds like me" | Drafts or edits in your voice, using a style memory it builds up over time at `02 Areas/Writing Voice.md`. |
| "make a skill that …" | Writes a new skill file for something you find yourself doing over and over. More on this below. |

One thing worth understanding, because it's what makes the two halves work together: the wikilinks you make aren't decoration. When Claude opens a meeting note and sees `related-to: "[[Website Refresh]]"`, it follows the link and reads the project page. If your daily note links to a meeting and that meeting links back to a project, Claude can trace a whole week of your work without you explaining any of it. Linking generously is the cheapest thing you can do to make the assistant half of this useful.

## Leveling up

**Integrations.** Connect Claude to your calendar and email (Microsoft 365 and Google both have connectors) and the workflows start compounding. My morning-briefing skill reads my inbox and calendar, checks them against my project notes, and writes the day's priorities into my daily note. It runs on the same foundation you're holding, plus two connectors and one more skill.

**More plugins.** There are thousands of community plugins, and whatever annoys you about Obsidian, one of them probably fixes it. TaskNotes is my case in point. My task list lived in Todoist for years, a separate app with its own sync and its own inbox to ignore. Then I found a plugin that turns the vault itself into a to-do app, and Todoist went in the bin the same week. Deeper Templater use belongs here too, once you're comfortable poking at template code.

**Schedules.** Briefings and audits that show up on a timer instead of waiting for you to ask; a periodic "tidy my vault" sweep is a reasonable first one.

**Version control.** The vault is just files, so git works on it. Commit now and then, or ask Claude to, and you get every note's history, readable diffs when Claude changes something, and a way to sync between machines that can't silently eat your data. Cloning this repo already put you inside a git repository.

**Growing the system.** The `improve-this-system` skill exists for this. Anything you notice yourself repeating, like summarizing the week every Friday or pulling action items out of meeting notes, can become a skill: say "make a skill that does X" and Claude writes the file. Claude also keeps a running list of friction it notices in `02 Areas/Local Life Manager/Backlog.md`, and "groom the backlog" walks you through it. A year in, what you're running won't look much like what you cloned.

If you build something interesting on top of this, or get stuck partway through, come talk to me.

---

MIT licensed. See [LICENSE](LICENSE).
