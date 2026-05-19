---
name: handoff
description: Create a concise handoff for another agent or future session to continue the work without replaying the conversation. Use when the user asks for a handoff, session summary, continuation note, or context transfer.
---

# Handoff

## Scope

- A current task, session, branch, PR, issue, or requested future focus.
- If no file path is provided, return the handoff inline.

## Workflow

1. **Identify purpose**. State what the next agent or session is expected to do.
2. **Summarize state**. Capture completed work, current branch/status, important decisions, and known constraints.
3. **Reference artifacts**. Link to files, issues, PRs, docs, commits, or commands instead of duplicating them.
4. **List next steps**. Provide ordered, actionable steps with blockers and validation commands where useful.
5. **Call out risks**. Include unresolved questions, failing checks, assumptions, and areas not inspected.
6. **Choose location**. Write inline by default, or to a user-requested path when a file is needed.

## Output

- Purpose of the next session
- Current state and decisions
- References to artifacts
- Next steps
- Risks, unknowns, and validation gaps

## Guardrails

- Do not duplicate long content already captured elsewhere.
- Do not use temporary files for durable handoffs unless the user asks.
- Do not hide uncertainty; make unknowns explicit.
- Keep the handoff practical enough for a fresh agent to act on immediately.
