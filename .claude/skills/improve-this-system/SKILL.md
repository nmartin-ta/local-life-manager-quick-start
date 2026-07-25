---
name: improve-this-system
description: Use when the user wants to change how this system itself works — "make a skill for X", "that skill did the wrong thing", "add a workflow", "update CLAUDE.md", "I keep doing X manually". Creates new skills, refines existing ones, keeps CLAUDE.md current.
---

# Improve This System

The kit is a seed. This skill grows it. Three jobs:

## 1. Create a new skill

When the user describes a workflow they repeat ("every Friday I…", "make a skill that…"):

1. Restate the workflow as trigger → steps → output. Confirm.
2. Create `.claude/skills/<kebab-name>/SKILL.md` in exactly this shape:

    ---
    name: <kebab-name>
    description: Use when <triggering situations, including 3–5 phrases the user would actually say>.
    ---
    # <Title>
    <Numbered steps. Name exact files and folders. State what to ask the user vs. do automatically. End with what "done" looks like.>

3. Keep it under ~50 lines. One skill = one workflow; if it needs modes, two clear modes max (see the `ideas` skill).
4. If the new workflow changes vault conventions (new folder, new frontmatter field), update `CLAUDE.md` → Vault conventions in the same pass.

## 2. Refine an existing skill

When a skill run went wrong: ask what the user expected, read the skill file, find the gap (missing rule, wrong trigger, ambiguous step), propose the specific edit, apply on approval. Make the smallest change that fixes the failure — don't rewrite the whole skill.

## 3. Keep CLAUDE.md current

When the user's context shifts (new role, new preferences, conventions drifting from reality), update the relevant CLAUDE.md section. Keep the whole file under ~80 lines — if it's growing past that, something belongs in a skill instead.

## Rules

- Never edit `.obsidian/` or plugin files from this skill.
- Show the user any new/edited skill file content before saving.
- After creating a skill, tell the user a phrase that will trigger it and suggest trying it now.
