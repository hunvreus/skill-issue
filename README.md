# Skill Issue

Small agent skills for real software work.

This repo is an experiment in no-nonsense, just-in-time engineering skills. The goal is not to micromanage the model or turn every workflow into a process framework. The goal is to give agents a few sharp defaults for work that commonly goes wrong: debugging without a repro, reviewing without findings, refactoring without validation, documenting guessed behavior, and releasing without checking the basics.

## Philosophy

- Skills should be concise and composable.
- Skills should describe the shape of work, not every implementation detail.
- Skills should leave judgment with the agent unless the task has known failure modes.
- Skills should be pulled in when useful, not become a project management system.
- Skills should encode practical engineering discipline: feedback loops, validation, small changes, clear outputs.

## Skills

- [`audit`](./skills/audit/SKILL.md): assess a new or unfamiliar project and identify the highest-value next actions.
- [`debug`](./skills/debug/SKILL.md): reproduce, isolate, and fix broken behavior.
- [`deploy`](./skills/deploy/SKILL.md): set up or validate app deployment.
- [`document`](./skills/document/SKILL.md): create or update project docs from verified behavior.
- [`handoff`](./skills/handoff/SKILL.md): summarize work so another session can continue.
- [`investigate`](./skills/investigate/SKILL.md): investigate live app or deployment issues.
- [`prototype`](./skills/prototype/SKILL.md): build throwaway prototypes that answer one question.
- [`refactor`](./skills/refactor/SKILL.md): simplify code while preserving behavior.
- [`release`](./skills/release/SKILL.md): prepare and validate releases.
- [`review`](./skills/review/SKILL.md): review changes for actionable issues.
- [`test`](./skills/test/SKILL.md): add, repair, or drive behavior tests.

## Skill Style

Preferred shape:

```md
# Verb

## Scope
## Workflow
## Output
## Examples
## Guardrails
```

`Examples` is optional. Use it only when examples clarify categories or materially improve behavior.

Keep `SKILL.md` frontmatter to `name` and `description`. Put UI-facing metadata in `agents/openai.yaml`.

## Agent Templates

Reusable `AGENTS.md` templates live in [`templates/agents`](./templates/agents/).

- [`js-react-fullstack`](./templates/agents/js-react-fullstack.md): `AGENTS.md` template for TypeScript full-stack web apps with React UI, shadcn component conventions, Drizzle schemas/migrations, and separated `src/components`, `src/lib`, and `src/server` ownership.
