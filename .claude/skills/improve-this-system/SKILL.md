---
name: improve-this-system
description: Use when the user wants to change how this system itself works — "make a skill for X", "that skill did the wrong thing", "add a workflow", "update CLAUDE.md", "I keep doing X manually". Creates new skills, refines existing ones, keeps CLAUDE.md current.
---

# Improve This System

This skill changes how the system itself works. Four jobs:

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
4. If the new workflow changes vault conventions (new folder in `my-obsidian-vault/`, new frontmatter field), update `CLAUDE.md` → Vault conventions in the same pass.

## 2. Refine an existing skill

When a skill run went wrong: ask what the user expected, read the skill file, find the gap (missing rule, wrong trigger, ambiguous step), propose the specific edit, apply on approval. Make the smallest change that fixes the failure. Don't rewrite the whole skill.

## 3. Keep CLAUDE.md current

When the user's context shifts (new role, new preferences, conventions drifting from reality), update the relevant CLAUDE.md section. Keep the whole file under ~80 lines. If it's growing past that, something belongs in a skill instead.

## 4. Groom the backlog

When the user says "groom the backlog": read the `## Open` section of `my-obsidian-vault/02 Areas/Local Life Manager/Backlog.md` (Claude's observer notes and the user's own gripes accumulate there). Present the items as a numbered list, each with a recommendation: **act now** (via jobs 1–3), **keep** (not ripe yet), or **drop**. Execute what the user approves, then check off or remove the handled items.

## Rules

- Never edit `.obsidian/` or plugin files from this skill.
- One skill = one workflow. Don't bolt a second workflow onto an existing skill.
- Don't systematize something that happened once; wait until it's clearly a pattern.
- Show the user any new/edited skill file content before saving.
- After creating a skill, tell the user a phrase that will trigger it and suggest trying it now.
