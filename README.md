# Skills

My agent skills. Small files you can edit. They work with any model.

Each skill is a folder with a `SKILL.md`. Add a new folder when you add a skill.

## Install

Any app that loads [Agent Skills](https://agentskills.io).

```bash
npx skills@latest add Adolanium/skills
```

Pick which skills to take, and which apps get a copy.

Or copy a skill folder into the place your app reads skills from. That is often `.agents/skills/<name>` in a project. You own the files. Nothing changes unless you change it.

## Skills

The agent can pick these on its own, and you can type them.

- **[hinge](./hinge/SKILL.md)** - Find the claim that would flip an ad, post, or pitch. Returns Take, Wait, or Walk.
- **[ffmain](./ffmain/SKILL.md)** - Fast-forward main from upstream, then push origin.
- **[new-skill](./new-skill/SKILL.md)** - Add a skill folder that follows these house rules.
- **[own-page](./own-page/SKILL.md)** - Check your page for the claim a reader would walk on.
- **[the-row](./the-row/SKILL.md)** - Read the right row of a table, filing, or chart.

## Adding a skill

1. Make `<name>/SKILL.md`.
2. The `name:` at the top must match the folder name.
3. The `description:` is one sentence, 60 characters or fewer, ending with a period. That cap is on purpose. Do not raise it. Do not repeat the skill name. Put "use when" lines in the skill body. The skill list only shows that short line, so it has to say what the skill does.
4. Keep `SKILL.md` short. Extra notes go in `references/`. Output shape goes in `templates/`.
5. Add a line to the list above.

See `AGENTS.md` in this folder for the same rules, written for an agent.
