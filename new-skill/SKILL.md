---
name: new-skill
description: Add a skill folder that follows these house rules.
license: MIT
---

# New skill

Add one skill to this collection. Match the house rules. Do not invent a new style.

## When to Use

- User says "add a skill", "new skill", "write a skill for X", or "put another skill in this folder."
- User wants a skill that will live next to `hinge` and the rest of this set.

Don't use for:

- Editing an existing skill in place (open that skill and change it).
- Writing a skill for some other collection with other rules.
- A one-off prompt with no folder to save.

## Need first

- Read `../AGENTS.md` if it is there. Those rules win.
- If `../AGENTS.md` is missing, use the rules in this file. Do not guess a longer style.
- You must be able to write files in the collection folder (the parent of this skill).

## Steps

### 1. Name it

Lowercase letters, digits, and hyphens. Must match the folder name. 2 to 64 characters. If the user did not give a name, propose one short name and wait.

Do not reuse a folder that already exists.

### 2. Write the description and count it

One sentence. 60 characters or fewer. Ends with a period. Does not repeat the skill name. No sales words.

Count the characters. If it is over 60, cut it. Put "use when" lines in the skill body, not in `description`.

That cap is on purpose. Do not raise it.

### 3. Write the body

Same shape as the skills already in this folder:

- Short intro (what it does, what it will not do)
- When to Use, and Don't use for
- Need first
- Steps with a done check at the end of each, when it matters
- Watch for
- You're done when

Simple English. Short words. Contractions are fine. No em dashes. No semicolons in prose. No sales talk.

Keep `SKILL.md` short. Extra notes go in `references/`. Output shape goes in `templates/`.

### 4. Write the files

Collection root is the parent of this `new-skill` folder.

Create:

- `<name>/SKILL.md`
- `references/` or `templates/` only if the body points at them
- `evals/evals.json` with a few cases that test the real job, not just headings

Then add one line to `../README.md` under Skills.

Use `templates/skill.md` as the empty shape.

### 5. Check before you stop

- `name:` matches the folder.
- `description` is 60 characters or fewer. You counted.
- No em dashes or semicolons in the prose.
- No named agent product.
- `README.md` has the new row.

## Watch for

- A long "use when" paragraph in `description`.
- Copying someone else's voice.
- A skill that only points at other skills and has no job of its own.
- Saving the folder in the wrong place (inside `new-skill/` instead of next to it).

## You're done when

The new folder exists, the description is 60 or under, and the root README lists it.
