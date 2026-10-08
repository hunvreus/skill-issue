---
name: overhaul
description: Plan and execute a cautious, multi-step improvement effort for a repository or major subsystem. Use when the user asks for a broad cleanup, modernization, technical debt pass, large refactor, or coordinated improvement across architecture, tests, docs, performance, reliability, and maintainability.
---

# Overhaul

## Workflow

1. **Agree on scope**. Goals, non-goals, and whether behavior changes are allowed.
2. **Baseline**. Run available tests, typecheck, lint, and build. Record existing failures before changing anything.
3. **Rank issues**. Order findings in scope by impact, risk, and confidence.
4. **Propose a wave plan**. Reviewable chunks, each with scope, validation, and risk.
5. **Stop for sign-off**. Ask the user to approve the plan and choose: check in after each chunk, or run through and report at the end.
6. **Execute chunk by chunk**. Edit, validate, update docs, summarize. Pause if risk rises or the plan needs to change.
7. **Close**. Re-run the baseline checks and report behavior changes, remaining risks, and follow-ups.

## Guardrails

- Overhaul is not a license to rewrite. Preserve behavior unless the user approves changes.
- No broad edits before sign-off.
- One concern per chunk; do not bundle unrelated risky changes.
- Tie performance work to a measurement or a stated hypothesis.
- Ask before removing APIs, config, migrations, or docs that may be intentional.
