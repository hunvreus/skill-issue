---
name: debug
description: Debug failing, flaky, slow, or incorrect behavior with a reproducible feedback loop. Use when something is broken, throwing, failing tests, behaving unexpectedly, or showing a performance regression.
---

# Debug

## Input

- A bug report, failing command, test, error, performance complaint, repro steps, or affected area.
- Use explicit input first; otherwise infer from context, recent edits, selected files, or branch.
- Safest default: find an agent-runnable repro before patching.

## Workflow

1. **Build a feedback loop**. Reproduce the issue with a runnable command, test, script, request, or browser flow.
2. **Confirm the symptom**. Verify the repro matches the user's reported behavior, not a nearby failure.
3. **Minimize the repro**. Reduce inputs, state, or steps until the failing behavior is clear.
4. **Form hypotheses**. List 2-4 falsifiable causes and test one at a time.
5. **Instrument narrowly**. Add targeted logs, assertions, debugger probes, or measurements only where they distinguish hypotheses.
6. **Fix the root cause**. Keep the change scoped to the proven cause.
7. **Add regression coverage**. Add or update a test when there is a suitable behavior-facing seam.
8. **Clean up**. Remove temporary probes, scripts, and logs.

## Output

- Repro used
- Root cause
- Fix applied
- Regression coverage added or skipped
- Validation run

## Guardrails

- Do not patch before reproducing unless reproduction is impossible.
- If no repro is possible, state what was tried and what artifact or access is needed.
- Do not leave temporary debug logs, scripts, or instrumentation behind.
- For performance issues, measure before and after.
