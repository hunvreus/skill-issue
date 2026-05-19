---
name: audit
description: Audit a new or unfamiliar project to understand its structure, health, risks, documentation gaps, and next actions. Use when initially entering a repo, assessing project quality, preparing onboarding, or asking what should be improved first.
---

# Audit

## Scope

- A repository, project path, subsystem, branch, or explicit audit question.
- If no scope is provided, audit the current project at a high level.

## Workflow

1. **Map the project**. Identify purpose, stack, entry points, package structure, runtime, and ownership boundaries.
2. **Find commands**. Locate install, dev, test, lint, typecheck, build, release, and deploy commands.
3. **Run safe checks**. Execute available non-destructive checks when practical; record missing or failing checks.
4. **Review docs**. Check README, architecture docs, API docs, devops docs, runbooks, and examples for gaps or stale claims.
5. **Inspect risk areas**. Review security, dependencies, config, migrations, data handling, error paths, observability, and release/deploy posture.
6. **Identify issues**. Produce prioritized findings with evidence, impact, and suggested next action.
7. **Fill obvious docs gaps**. If requested, update small missing docs discovered during the audit.

## Output

- Project map
- Available commands and check results
- Findings ordered by severity or leverage
- Documentation gaps
- Suggested next actions
- Work explicitly not audited

## Guardrails

- Do not make broad changes during an audit unless the user asks.
- Do not run destructive commands or deploys.
- Distinguish observed facts from guesses.
- Prefer actionable findings over generic best-practice lists.
