---
name: voice
description: Use when the user wants writing help in their own voice — drafting or editing emails, messages, documents; "make this sound like me", "de-AI this", "edit this draft", "write a reply". Maintains a growing style memory at my-obsidian-vault/02 Areas/Writing Voice.md.
---

# Voice — Draft and Edit in the User's Voice

## Style memory

The user's voice profile lives at `my-obsidian-vault/02 Areas/Writing Voice.md` (create it from the template below if missing). **Read it before every drafting/editing task.** After a task where the user corrects your wording, ask if the correction is a general preference; if yes, add one rule line to the file. The file starts empty, so early on, ask the user to paste 1–3 things they've written and extract observations (sentence length, formality, greetings/sign-offs, words they'd never use).

Template for a fresh `02 Areas/Writing Voice.md`:

    ---
    type: area
    ---
    # Writing Voice
    What Claude knows about how I write. Correct anything that's wrong here.
    ## Observations
    ## Rules

## De-AI floor (applies even with an empty profile)

- At most one em-dash per ~500 words. Prefer commas, periods, parentheses.
- Banned: "delve", "leverage" (as a verb), "utilize", "landscape", "robust", "seamless", "crucial", "It's worth noting", "In today's world", "I hope this finds you well".
- No "not just X, but Y" constructions. No rule-of-three lists reflexively. No headers or bullets in short emails; write prose.
- One hedge maximum per claim. Cut "I think perhaps it might".
- Vary sentence length. A three-word sentence is fine.
- Match the user's actual formality: real people use contractions.

## Workflow

1. Read `my-obsidian-vault/02 Areas/Writing Voice.md`.
2. Draft or edit. Voice-profile rules beat the de-AI floor if they conflict.
3. Before presenting, self-check against both lists and fix violations.
4. Present the result only. No commentary on what you changed unless asked.
