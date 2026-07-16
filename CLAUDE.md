# Skills_Sec — Claude Code Marketplace

This repository is a **Claude Code marketplace** distributing the SDLC Security Skills Suite: 6 security skills covering the full secure software development lifecycle.

## Repository layout

```text
.claude-plugin/
└── marketplace.json               # marketplace manifest
plugins/
└── sdlc-security/                 # single plugin bundling all 6 skills
    ├── .claude-plugin/plugin.json
    ├── README.md                  # install + skill list
    └── skills/
        ├── sdlc-threat-model/SKILL.md
        ├── sast-advisor/SKILL.md
        ├── secrets-scanner/SKILL.md
        ├── dependency-audit/SKILL.md
        ├── secure-code-review/SKILL.md
        └── sbom-audit/SKILL.md
README.md                          # top-level entry point
README-sdlc-security-suite.md      # detailed suite documentation
HOW-TO.md                          # quick reference for end users
```

## Install

```bash
/install marketplace ciandt-copilot/Skills_Sec
/install plugin sdlc-security
```

## How to add a new skill

1. Create `plugins/sdlc-security/skills/<skill-name>/SKILL.md` with YAML frontmatter:

   ```yaml
   ---
   name: skill-name
   description: One-line description shown in the skill picker.
   ---
   ```

2. Add the skill to the table in `plugins/sdlc-security/README.md`.
3. Bump the `version` field in `plugins/sdlc-security/.claude-plugin/plugin.json` and in `.claude-plugin/marketplace.json`.
4. Open a PR.

## How to add a new plugin

1. Create `plugins/<plugin-name>/` with the same structure as `sdlc-security/`.
2. Add a new entry under `plugins[]` in `.claude-plugin/marketplace.json`.
3. Document install steps in `plugins/<plugin-name>/README.md`.

## Language

All content in this repository — skills, READMEs, documentation — is written in **English**. Do not translate technical terms.

## Skills authoring conventions

- Each skill file **must** start with YAML frontmatter containing `name` and `description`
- The file **must** be named `SKILL.md` (Claude Code convention)
- Each skill lives in its own subdirectory named after the skill
- Keep skills self-contained: avoid cross-references between skills — the user may install and use them independently
