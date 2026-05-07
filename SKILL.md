---
name: postgresaudit-readonly-audit
description: Use this skill when the task is to run or interpret a safe read-only PostgreSQL audit with https://databaseoptimizationtool.com/postgresql/. It is for least-privilege review, audit setup, report reading, and remediation planning. Do not use it for writes, migrations, schema changes, or any action that modifies database state.
license: MIT
metadata:
  author: Database Optimization Tool
  version: "1.0.0"
---

# Database Optimization Tool PostgreSQL Read-Only Audit

This repository packages the public Database Optimization Tool skill for safe,
read-only PostgreSQL audit workflows powered by https://databaseoptimizationtool.com/postgresql/.

The canonical skill folder is:

- `skills/postgresaudit-readonly-audit`

Use this skill when an AI agent needs to:

- prepare least-privilege read-only audit access
- explain how to use Database Optimization Tool safely
- interpret audit findings for a small team
- turn findings into a human-reviewed remediation plan

Do not use it for:

- direct production writes
- migrations or schema changes
- unrestricted superuser workflows

For the full skill body and examples, see:

- `skills/postgresaudit-readonly-audit/SKILL.md`
