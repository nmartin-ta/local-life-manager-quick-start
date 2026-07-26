---
name: tasks
description: Use when the user wants to create a task ("make a task", "add a task", "remind me to") or round up commitments scattered in their notes ("triage my notes", "find my tasks", "what did I commit to?"). Creates TaskNotes in 05 Tasks/TaskNotes/; triage mode sweeps dailies and meeting action items.
---

# Tasks — Capture and Triage

Tasks are notes: a file in `my-obsidian-vault/05 Tasks/TaskNotes/` whose frontmatter carries a `task` tag. The TaskNotes plugin turns them into a to-do system (views live in `05 Tasks/Views/`). Statuses: `open`, `done`, `someday` (parked, no dates). Two modes — detect from the request.

## Task note shape

Filename = the task title. Frontmatter only:

    ---
    status: open
    priority: normal
    due: YYYY-MM-DD          # hard deadline — omit if none
    scheduled: YYYY-MM-DD    # when the user plans to do it — omit if none
    related-to:
      - "[[Project or Area note]]"
    dateCreated: <ISO timestamp>
    dateModified: <ISO timestamp>
    tags:
      - task
    ---

Omit `related-to` if nothing fits. Title style: verb first, specific ("Draft sitemap", not "Sitemap stuff").

## Capture mode

The user names a task. **Before creating, check for duplicates**: search open tasks in `05 Tasks/TaskNotes/` for similar titles; if a close match exists, say so and ask instead of creating. Otherwise create the note, confirm in one line. If the user gave a date, decide `due` (deadline) vs `scheduled` (plan) from their wording.

## Triage mode

1. Sweep recent notes for commitments: unchecked `- [ ]` items in `04 Meetings/` notes, and task-like jottings in the last ~2 weeks of `00 Daily Notes/` ("need to", "must", "follow up", "remind", "by Friday").
2. Cross-reference every candidate against existing tasks (open AND done) — never propose a duplicate.
3. Present a numbered list: each candidate with source note, proposed title, proposed dates, and a verdict (new / duplicate of X / not really a task). The user answers by number.
4. Create the approved ones. Do not modify the source notes — the jotting stays where it was; the task is the tracked copy.

A task the user says is finished: set `status: done` and add `completedDate: YYYY-MM-DD`. Never delete task notes.
