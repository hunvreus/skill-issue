---
name: prototype
description: Build a clearly throwaway prototype to answer one design, logic, state, or UI question before committing to production code. Use when the user asks to prototype, mock up, try a design, sanity-check a model, or make something exploratory.
---

# Prototype

## Input

- A design, state model, UI idea, interaction, algorithm, integration, or uncertainty to explore.
- Use explicit input first; otherwise infer the question from context.
- Safest default: define the question before coding.

## Workflow

1. **State the question**. Define the single question the prototype must answer.
2. **Choose the shape**. Use a terminal, script, fixture, route, component, or mock UI that answers the question fastest.
3. **Mark it throwaway**. Name and place the prototype so it cannot be mistaken for production code.
4. **Make it runnable**. Provide one command or obvious path to exercise it.
5. **Expose state**. Print or render the relevant inputs, transitions, outputs, and edge cases.
6. **Capture the answer**. Record what was learned in the final report, docs, issue, or follow-up plan.
7. **Delete or absorb**. Remove the prototype or fold the validated idea into real code when the question is answered.

## Output

- Question answered
- Prototype location and run command
- Findings
- What should be deleted, kept, or absorbed into production code

## Guardrails

- Do not add persistence unless persistence is the question being tested.
- Do not polish beyond what is needed to learn.
- Do not let exploratory code silently become architecture.
- State what is intentionally not production-ready.
