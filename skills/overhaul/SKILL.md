---
name: overhaul
description: Plan and execute a cautious, multi-step improvement effort for a repository or major subsystem. Use when the user asks for a broad cleanup, modernization, technical debt pass, large refactor, or coordinated improvement across architecture, tests, docs, performance, reliability, and maintainability.
---

# Overhaul

## Input

- A whole repository, platform, major subsystem, or long-running improvement program.
- Use explicit input first; otherwise infer from context, recent edits, selected files, or branch.
- Safest default: plan first and get user signoff before broad edits.

## Workflow

1. **Define the target**. Identify goals, scope, constraints, non-goals, and whether behavior changes are allowed.
2. **Baseline first**. Find available commands and run safe checks where practical: tests, build, typecheck, lint, performance or deploy checks. Record failures before changing code.
3. **Map the system**. Identify entry points, core modules, data flow, external dependencies, deploy path, and docs that matter for the requested scope.
4. **Find leverage**. Rank issues by user impact, correctness risk, maintenance cost, performance impact, and confidence. Separate observed facts from guesses.
5. **Propose a wave plan**. Break work into reviewable chunks with explicit scope, validation, risks, and expected outcome for each chunk.
6. **Get signoff**. Before editing, ask the user to approve the plan and choose execution style: validate after each major chunk or proceed through the approved plan and report at the end.
7. **Execute in chunks**. For each approved chunk: inspect, edit narrowly, validate, document relevant changes, and summarize what changed.
8. **Reassess between chunks**. Pause for user validation when requested, when risk increases, or when the plan needs to change.
9. **Close the loop**. Re-run relevant checks, summarize completed work, behavior changes, docs changes, remaining risks, and follow-up work.

## Output

- Baseline checks and measurements
- System map
- Prioritized findings and risks
- Approved wave plan
- Per-chunk validation results
- Behavior changes, if any, called out explicitly
- Documentation updated or gaps identified
- Remaining risks and follow-ups

## Examples

- `overhaul this app without changing behavior`
- `plan a technical debt cleanup for this repo`
- `modernize this subsystem, but ask before each big chunk`
- `review the platform and propose a multi-step improvement plan`

## Guardrails

- Do not treat overhaul as permission for a rewrite. Preserve behavior unless the user explicitly approves behavior changes.
- Do not start broad edits before baseline, system map, plan, and user signoff.
- Do not bundle unrelated risky changes into one diff.
- Do not optimize from vibes; tie performance work to measurements or a clearly stated hypothesis.
- Ask before removing behavior, APIs, config, migrations, or docs that may be intentional.
- Use `review`, `refactor`, `test`, `document`, `deploy`, or `second-opinion` as follow-up modes when a chunk needs that sharper workflow.
