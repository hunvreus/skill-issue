---
name: refactor
description: Review and refactor code within a specified scope. Use when the user asks to clean up, simplify, reduce duplication, remove dead code, or improve code quality in a file, module, or broader area of the codebase.
---

# Refactor

## Scope

- A file, module, package, feature area, diff, or project scope to refactor.
- If no scope is provided, confirm whether to inspect the whole project before changing code.

## Workflow

1. **Confirm scope**. If no scope is provided, confirm with the user whether they want to refactor the entire project.
2. **Identify surface**. Find files and direct dependencies that may need review or change.
3. **Run baseline checks**. Use available tests, typecheck, lint, or build commands for the scope. Note missing or failing tooling.
4. **Identify refactors**:
    - Dead code: unused functions, branches, flags, adapters, and stale comments/docs.
    - Duplication: repeated logic, validation, mapping, and query patterns.
    - Unnecessary complexity: deep nesting, mixed responsibilities, ambiguous naming, and over-abstraction.
    - Evidence-backed optimization: hot loops, N+1 queries, repeated expensive work.
5. **Plan changes**. Confirm when changes may affect behavior or remove intentional code.
6. **Apply safe changes incrementally**. Prefer small, reviewable edits.
7. **Validate behavior**:
    - Re-run available baseline checks plus targeted tests for touched areas.
    - Ensure no accidental API, schema, or side-effect regressions.

## Output

- Scope reviewed
- Refactors applied
- Behavior preserved or intentionally changed
- Validation run
- Remaining risks or follow-up work

## Guardrails

- Do not change behavior to satisfy style preferences alone.
- Do not remove intentional features without confirmation.
- Do not introduce broad rewrites when focused refactors solve the problem.
- Keep type boundaries strict; avoid loose typing unless narrowly justified.
