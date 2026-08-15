# Skills collection

This folder is a personal set of skills. Each child folder is one skill.

## The 60 character cap is on purpose

Do not write a long `description`. The skill list only keeps a short line. A long one gets cut, and the agent will not know when to use the skill.

This is a hard rule for every new skill in this folder. It is not a hint. If another model or app is writing a skill here, follow this:

- `description` is one sentence.
- 60 characters or fewer. Count them.
- Ends with a period.
- Do not repeat the skill name.
- No sales words.
- When to use, trigger phrases, and when not to use go in the skill body, not in `description`.

If you draft a description over 60 characters, shorten it before you finish. Do not "improve" it by making it longer.

## New skill

- Path: `<name>/SKILL.md` with `name: <name>` at the top.
- Follow the 60 character cap above.
- Keep `SKILL.md` short. Extra notes go in `references/`. Output shape goes in `templates/`.
- Add one line to `README.md`.

## Editing

- Say each rule in one place. Do not copy the same table into two files.
- If a line does not change what the agent does, cut it.
- Do not name a specific agent product in these files.
