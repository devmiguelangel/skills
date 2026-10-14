# Skills

Reusable agent skills, installable with [Vercel's Skills CLI](https://github.com/vercel-labs/skills).

## Structure

```text
skills/
├── conventional-commits/
│   └── SKILL.md
└── notion-ticket-tracker/
    ├── SKILL.md
    └── references/
        └── template.md
```

Each skill belongs in `skills/<skill-name>/SKILL.md`. The file requires YAML frontmatter with `name` and `description`, followed by Markdown instructions for the agent. Use lowercase letters, digits, and hyphens for skill names, and match the folder name to the skill name.

Available skills:

- `conventional-commits` generates specific Conventional Commit messages with lowercase subjects, a 72-character limit, and breaking-change markers.
- `notion-ticket-tracker` creates, updates, or migrates tickets in a Notion Jira-style database, including exact-source Markdown imports and supporting files.

Add other skills as sibling folders. Optional `scripts/`, `references/`, and `assets/` folders can live inside each skill when needed.

## Check local discovery

From the repository root:

```sh
npx skills add . --list
```

## Install

Once the files are committed and pushed to GitHub:

```sh
npx skills add devmiguelangel/skills
```

To list available skills or install a specific one:

```sh
npx skills add devmiguelangel/skills --list
npx skills add devmiguelangel/skills --skill conventional-commits
npx skills add devmiguelangel/skills --skill notion-ticket-tracker
```

No package.json or repository-level skill manifest is required for discovery.
