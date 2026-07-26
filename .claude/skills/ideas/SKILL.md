---
name: ideas
description: Use when the user wants to capture a thought ("capture an idea", "note this down", "add to my ideas") or review accumulated ones ("review my ideas", "what's in my ideas list?"). Captures to the idea garden at my-obsidian-vault/02 Areas/Local Life Manager/Ideas.md; review mode sweeps #idea tags, then transfers and clusters.
---

# Ideas — Capture and Review

The idea garden is `my-obsidian-vault/02 Areas/Local Life Manager/Ideas.md`: an `## Inbox` for raw captures, thematic `## <Cluster>` sections for organized ones. Two modes — detect from the request. Commitments and to-dos ("remind me to", "I need to do X") are the `tasks` skill's job — an idea is a thought worth keeping, not an action.

## Capture mode

The user gives you a thought. Append one bullet under `## Inbox`:

`- **YYYY-MM-DD** — <the idea, tightened but in their words>`

If it clearly relates to an existing project or area, add the wikilink inline. Confirm in one line. **Do not** start organizing, expanding, or researching the idea — capture means capture.

## Review mode

1. Gather: everything under `## Inbox`, plus anything tagged `#idea` anywhere — sweep `00 Daily Notes/` especially, since `#idea` jottings under timestamp headings are the main overflow.
2. Transfer and organize inside Ideas.md: move Inbox items into thematic `## <Cluster>` sections (create clusters as themes emerge; an idea appears once, never in both Inbox and a cluster) and copy swept `#idea` jottings into the right cluster. A one-line note on why an idea is kept helps future reviews. **Never edit the source notes** — the daily-note jotting stays where it was; Ideas.md is the organized copy.
3. For each cluster or standalone idea, propose ONE of:
   - **Promote** — it's really a project: offer to create `01 Projects/<Name>/` with a `<Name>.md` folder note (from `98 Templates/Template, Project.md`) and move the idea content there.
   - **File** — it belongs inside an existing project or area note: offer to move it there as a linked bullet.
   - **Keep** — not ripe; leave it in its cluster, optionally reworded.
   - **Drop** — dead; delete the line (only with approval).
4. Present as a numbered list; the user answers by number. Apply approved actions, remove promoted/filed/dropped lines from Ideas.md, and confirm.
