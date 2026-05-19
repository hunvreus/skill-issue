---
name: test
description: Add, update, or repair tests for behavior, regressions, and test-first development. Use when the user asks for tests, TDD, red-green-refactor, regression coverage, test repair, or behavior-driven implementation.
---

# Test

## Scope

- A behavior, bug, module, feature, failing test, or uncovered path to test.
- If no scope is provided, identify the public behavior and highest-risk paths before writing tests.

## Workflow

1. **Define behavior**. Identify the public interface and the behavior that matters to the user.
2. **Pick the first slice**. Choose one narrow behavior that proves the path end to end.
3. **Write or repair tests**. Prefer behavior-facing tests over implementation-detail tests.
4. **Use TDD when requested**. Red: write one failing test. Green: write the smallest implementation that passes. Repeat by slice.
5. **Refactor when green**. Simplify duplication, names, and module shape after tests pass.
6. **Validate**. Run relevant tests, typecheck, lint, or build commands.

## Output

- Behaviors covered
- Tests added, changed, or repaired
- Implementation changed, if any
- Validation run
- Remaining test gaps

## Guardrails

- Do not write all tests before all implementation when using TDD.
- Prefer tests through public interfaces over private functions and internal mocks.
- Do not refactor while tests are red.
- Keep test scope proportional to behavior risk.
