# Skill Issue

This is a toolkit of skills I use every day to write, test, document, and deploy software.

Agents know a lot but often need better defaults. They don't need to be micromanaged or forced into rigid processes; they just need a nudge in the right direction.

These skills try to do just that:

- They are concise and composable.
- They describe the shape of work, not every implementation detail.
- They leave judgment with the agent unless the task has known failure modes.
- They stay discrete instead of trying to become a full development lifecycle.

## Quickstart

Install the repo:

```sh
npx skills add hunvreus/skill-issue
```

Install every skill without prompting:

```sh
npx skills add hunvreus/skill-issue --all
```

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
- [`second-opinion`](./skills/second-opinion/SKILL.md): ask another local AI CLI to critique a proposal.
- [`test`](./skills/test/SKILL.md): add, repair, or drive behavior tests.

## Agent Templates

Reusable `AGENTS.md` templates live in [`templates/agents`](./templates/agents/).

- [`js-react-fullstack`](./templates/agents/js-react-fullstack.md): `AGENTS.md` template for TypeScript full-stack web apps with React UI, shadcn component conventions, Drizzle schemas/migrations, and separated `src/components`, `src/lib`, and `src/server` ownership.
