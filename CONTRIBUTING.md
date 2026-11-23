# Adding to the Library

Family Members normally suggest additions through the **Proposal** form on the Alpha-Star website, which opens a pull request here. The Admin reviews and approves every Proposal before it is published.

## Layout

Each plugin under `plugins/` is a bundle someone installs by name. A plugin holds one or more Agents and the Skills they use:

```
plugins/<plugin-name>/
├── .claude-plugin/plugin.json      # name, version, description
├── agents/<agent-name>.md          # one file per Agent
└── skills/<skill-name>/SKILL.md    # one folder per Skill
```

Every plugin must also be listed in `.claude-plugin/marketplace.json`.

## Agent files

An Agent is a Markdown file with frontmatter, followed by its instructions:

```markdown
---
name: chef                 # lowercase, unique in the Library
description: ...           # what it's for and when to use it
model: sonnet              # the model it runs on; must be an Allowed Model to run in Chatrooms
skills:                    # Skills it uses, by name
  - meal-planning
---

Instructions in plain language.
```

## Skill files

A Skill is a folder containing `SKILL.md`, with `name` and `description` frontmatter followed by the instructions.

## Rules

- **Nothing personal.** This repo is public. No names, addresses, schedules, health details or anything else about family members.
- Bump the plugin's `version` in `plugin.json` when you change it, so installed copies update.
- Check your change with `claude plugin validate .` before opening a pull request.
