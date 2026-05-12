---
name: refactor
description: Review and refactor code within a specified scope. Use when the user asks to clean up, simplify, reduce duplication, remove dead code, or improve code quality in a file, module, or broader area of the codebase.
metadata:
  short-description: Clean up, simplify, and refactor code
---

# Refactor

## Workflow

1. **Confirm scope**. If no scope is provided, confirm with the user whether they want to refactor the entire project.
2. **Identify refactor surface**. Based on the scope, identify the files that may need to be reviewed and changed. This may include direct dependencies.
3. **Perform basic checks**: if tests, typecheck, lint, or build commands are available, run them for the defined surface. Note failures but do not block on missing tooling.
4. **Identify refactors**:
  - Dead code: unused functions, branches, flags, adapters, and stale comments/docs.
  - Duplication: repeated logic, validation, mapping, and query patterns.
  - Unnecessary complexity: deep nesting, mixed responsibilities, ambiguous naming, and over-abstraction.
  - Optimization opportunities only where evidence exists (hot loops, N+1 queries, repeated expensive work).
5. **Create plan and confirm**. Create a plan to address potential bug fixes and refactors identified in previous steps.
6. **Once confirmed, apply safe changes incrementally**. Prefer small, reviewable edits.
7. **Validate behavior**:
  - Re-run any available baseline checks plus targeted tests for touched areas.
  - Ensure no accidental API, schema, or side-effect regressions.
8. **Report**. Provide a summary of what was done and what may still be unaddressed.

## Guardrails

- Do not change behavior to satisfy style preferences alone.
- Do not remove intentional features without confirmation.
- Do not introduce broad rewrites when focused refactors solve the problem.
- Keep type boundaries strict; avoid loose typing unless narrowly justified.
