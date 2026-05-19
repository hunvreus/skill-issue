---
name: document
description: Create or update project documentation, README sections, architecture docs, API docs, examples, migration notes, devops docs, runbooks, or usage guides. Use when the user asks to document behavior, explain usage, update docs after code changes, or remove stale documentation.
---

# Document

## Scope

- A feature, behavior, module, command, API, release, operational procedure, or existing doc scope to document.
- If the request is broad, infer the most relevant scope from context; ask only when the audience or location is unclear.

## Workflow

1. **Identify audience**. Determine whether the docs are for users, contributors, operators, maintainers, or future agents.
2. **Choose location**. Update the closest existing doc. If none exists, create the smallest obvious doc.
3. **Verify behavior**. Read relevant code, tests, config, scripts, and existing docs before writing.
4. **Update cleanly**. Keep docs easy to scan and avoid parallel explanations that will drift.
5. **Use examples sparingly**. Prefer runnable commands, realistic config, and checked snippets.
6. **Prune stale content**. Remove or fix outdated docs discovered in the touched area.
7. **Validate**. Check links, commands, snippets, paths, and generated output where practical.

## Output

- Updated docs
- Behavior or source verified
- Validation performed
- Gaps or assumptions that remain

## Examples

- `README.md`: project purpose, setup, usage, common commands, contribution notes.
- `ARCHITECTURE.md`: stable system shape and tradeoffs when architecture is non-obvious.
- `docs/api.md`: simple external API contracts and examples.
- `docs/devops.md`: deploy path, environments, secrets, logs, monitoring, backups, and rollback.
- `docs/runbooks/`: step-by-step operational procedures when there is more than one to maintain.
- Colocated `README.md`: docs local to a package, module, or examples directory.

## Guardrails

- Do not document guessed behavior; verify against source or state the uncertainty.
- Keep docs concise, current, and task-oriented.
- Public modules and functions should document inputs, outputs, side effects, and failure modes when those are not obvious.
- Split docs only when audiences, lifetimes, or ownership differ.
