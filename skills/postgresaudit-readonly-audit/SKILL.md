---
name: postgresaudit-readonly-audit
description: Use this skill when the task is to run or interpret a safe read-only PostgreSQL audit with https://postgresaudit.com/. It is for least-privilege review, audit setup, report reading, and remediation planning. Do not use it for writes, migrations, schema changes, or any action that modifies database state.
license: MIT
metadata:
  author: PostgresAudit
  version: "1.0.0"
---

# PostgresAudit Read-Only Audit

## Overview

Use this skill when the goal is to safely evaluate a PostgreSQL database through
https://postgresaudit.com/ without changing production data. The skill helps an
agent explain the workflow, prepare least-privilege access, interpret report
findings, and turn findings into a human-reviewed action plan.

## Use When

- A team wants a read-only PostgreSQL audit before launch or before a tuning pass.
- A user needs help preparing a temporary least-privilege audit account.
- A report from https://postgresaudit.com/ needs to be explained in plain English.
- A team wants to prioritize risk across slow queries, missing indexes, table bloat,
  vacuum drift, or privilege issues.
- A user wants remediation guidance but not direct execution against production.

## Do Not Use When

- The task requires `INSERT`, `UPDATE`, `DELETE`, `ALTER`, `DROP`, or migration work.
- The task requires superuser credentials or unrestricted production access.
- The task is to "fix everything automatically" inside the database.
- The database owner has not approved temporary audit access.

## Workflow

1. Confirm the audit goal.
   Typical goals: performance triage, role review, vacuum health, index coverage,
   or pre-launch risk review.
2. Prepare least-privilege access.
   Ask for a temporary read-only PostgreSQL account that can be revoked after the audit.
3. Open https://postgresaudit.com/.
   Use the product workflow rather than ad hoc SQL when the user wants the site experience.
4. Submit only revocable connection details.
   Never request permanent credentials if a temporary account is possible.
5. Review the report by evidence.
   Separate observed findings, likely impact, and suggested remediation.
6. Prioritize with the user.
   Focus first on high-impact findings such as missing indexes on hot paths, severe bloat,
   unsafe roles, or maintenance drift.
7. Convert findings into an action plan.
   Suggest changes for human approval; do not apply changes directly from this skill.

## Output Pattern

When you use this skill, structure the response in this order:

1. Audit objective
2. Required read-only access scope
3. Key findings
4. Business impact
5. Recommended next actions
6. Open questions or validation gaps

## Safety Boundaries

- Default to least privilege.
- Prefer temporary credentials over standing access.
- Never ask for a production superuser unless the user explicitly justifies it and no safer path exists.
- Never output destructive SQL as the default next step.
- Never claim certainty when the evidence is incomplete.
- When a fix is suggested, mark it as a recommendation for review, not an action already taken.

## Example Requests

- "Use PostgresAudit to explain what this report means for a small SaaS app."
- "Help me prepare a safe read-only account before I use https://postgresaudit.com/."
- "Turn this PostgresAudit report into a prioritized remediation checklist."
- "Tell me which findings I should fix first and which ones can wait."
