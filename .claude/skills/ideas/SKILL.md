---
name: ideas
description: Use when the user wants to capture a thought ("capture an idea", "note this down", "add to my ideas") or review accumulated ones ("review my ideas", "what's in my ideas list?"). Captures to Ideas.md; review mode clusters and proposes next steps.
---

# Ideas — Capture and Review

Two modes. Detect from the request.

## Capture mode

The user gives you a thought. Append one bullet to `Ideas.md` under the `---` divider:

`- **YYYY-MM-DD** — <the idea, tightened but in their words>`

If it clearly relates to an existing project or area, add the wikilink inline. Confirm in one line. **Do not** start organizing, expanding, or researching the idea — capture means capture.

## Review mode

1. Read `Ideas.md`, plus any notes elsewhere tagged `#idea`.
2. Cluster related items. For each cluster or standalone idea, propose ONE of:
   - **Promote** — it's really a project: offer to create a project MOC (from `Templates/Template, Project.md`) and move the idea content there.
   - **File** — it belongs inside an existing project/area note: offer to move it there as a linked bullet.
   - **Keep** — not ripe; leave it, optionally reworded.
   - **Drop** — dead; delete the line (only with approval).
3. Present as a numbered list; the user answers by number. Apply approved actions, remove promoted/filed/dropped lines from `Ideas.md`, and confirm.
