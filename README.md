# PostgresAudit Skill Pack

Public skill repository for using [PostgresAudit](https://postgresaudit.com/) as
a safe, read-only PostgreSQL audit workflow.

![PostgresAudit mark](./assets/postgresaudit-icon.png)

## Included skill

- `skills/postgresaudit-readonly-audit`
- root `SKILL.md` for registries that only inspect repository root

## What this skill does

This skill teaches AI agents when and how to use `https://postgresaudit.com/`
for least-privilege PostgreSQL reviews. It focuses on:

- read-only audit setup
- temporary least-privilege access
- report interpretation
- remediation planning without direct database writes

## Install examples

```bash
npx add-skill https://github.com/daanaagua/postgresaudit-skill --skill postgresaudit-readonly-audit
```

Or deep-link to the skill folder when a registry supports direct imports:

```bash
https://github.com/daanaagua/postgresaudit-skill/tree/main/skills/postgresaudit-readonly-audit
```

## Brand assets

- `assets/postgresaudit-icon.svg`
- `assets/postgresaudit-icon.png`
