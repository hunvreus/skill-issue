---
name: document
description: Create or update project documentation, README sections, architecture docs, API docs, examples, migration notes, devops docs, runbooks, or usage guides. Use when the user asks to document behavior, explain usage, update docs after code changes, or remove stale documentation.
---

# Document

## Input

- A feature, behavior, module, command, API, release, operational procedure, or existing doc.
- Use explicit input first; otherwise infer from context, recent edits, selected files, or branch.
- Safest default: ask only when audience, ownership, or location is unclear.

## Workflow

1. **Identify audience and purpose**. Know whether the reader is a user, integrator, contributor, operator, maintainer, or future agent.
2. **Choose the owner**. Update the closest existing doc. Create a new doc only when audience, lifetime, or ownership clearly differs.
3. **Verify behavior**. Read relevant code, tests, config, scripts, schemas, and existing docs before writing.
4. **Separate facts by owner**. Product behavior, external contracts, repo workflows, and system mechanics should not duplicate each other.
5. **Update cleanly**. Keep docs scannable, concise, and current. Avoid parallel explanations that will drift.
6. **Use examples sparingly**. Prefer runnable commands, realistic config, checked snippets, and links to authoritative code or tests.
7. **Prune stale content**. Remove outdated docs, dead links, obsolete examples, and temporary review artifacts discovered nearby.
8. **Validate**. Check links, commands, snippets, paths, generated output, and any spec/doc sync mechanism where practical.

## Output

- Updated docs
- Audience and doc owner identified
- Behavior, source, or contract verified
- Validation performed
- Gaps or assumptions that remain

## Examples

- `README.md`: project purpose, setup, usage, common commands, contribution notes.
- `ARCHITECTURE.md`: stable system mechanics, data flow, invariants, and non-obvious tradeoffs.
- `docs/features/*.md`: expected product behavior, guarantees, edge cases, and user/agent-visible invariants.
- `docs/api/*.md`: external or agent-facing contracts, auth, response shapes, errors, and stability promises.
- `docs/development/*.md`: local setup, testing, migrations, safe change workflows, and operational procedures.
- `TODO.md` / `CHANGELOG.md`: unresolved work vs implemented visible changes; keep them separate.

## Guardrails

- Do not document guessed behavior; verify against source or state the uncertainty.
- Keep docs concise, current, and task-oriented.
- Public modules and functions should document inputs, outputs, side effects, and failure modes when those are not obvious.
- Split docs only when audiences, lifetimes, or ownership differ.
- Do not maintain duplicate private route catalogs or unvalidated specs. Code, tests, schemas, and generated artifacts are often the source of truth.
- Keep transient notes, audits, and baseline snapshots out of canonical docs unless they become durable decisions or work items.
- Prefer editing and pruning existing docs over adding new files.
