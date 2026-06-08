---
name: refactor
description: Review and refactor code within a specified scope. Use when the user asks to clean up, simplify, reduce duplication, remove dead code, or improve code quality in a file, module, or broader area of the codebase.
---

# Refactor

## Input

- A file, module, package, feature, diff, or project area to refactor.
- Use explicit input first; otherwise infer from context, recent edits, selected files, or branch.
- Safest default: ask before refactoring the whole project.

## Workflow

1. **Confirm input**. If no input is provided or implied, confirm before refactoring the entire project.
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

- Input reviewed
- Refactors applied
- Behavior preserved or intentionally changed
- Validation run
- Remaining risks or follow-up work

## Guardrails

- Do not change behavior to satisfy style preferences alone.
- Do not remove intentional features without confirmation.
- Do not introduce broad rewrites when focused refactors solve the problem.
- Keep type boundaries strict; avoid loose typing unless narrowly justified.
