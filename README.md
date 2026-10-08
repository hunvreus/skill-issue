# Skill Issue

This is a small set of skills I use to plan, release, deploy, and operate software.

Agents know a lot but often need better defaults. They don't need to be micromanaged or forced into rigid processes; they just need a nudge in the right direction.

These skills try to do just that:

- They are concise and composable.
- They describe the shape of work, not every implementation detail.
- They leave judgment with the agent unless the task has known failure modes.
- They stay discrete instead of trying to become a full development lifecycle.

## Quickstart

This repo is a skill pack for the `skills` CLI. The `SKILL.md` files define reusable agent workflows, `agents/openai.yaml` adds OpenAI/Codex-facing metadata, and `templates/` contains starter files grouped by category/tech, including `AGENTS.md` policies for app repos.

Install the repo:

```sh
npx skills add hunvreus/skill-issue
```

Install every skill without prompting:

```sh
npx skills add hunvreus/skill-issue --all
```

## License

[MIT](./LICENSE)

## Skills

- [`deploy`](./skills/deploy/SKILL.md): set up or validate app deployment.
- [`investigate`](./skills/investigate/SKILL.md): investigate live app or deployment issues.
- [`overhaul`](./skills/overhaul/SKILL.md): plan and run cautious multi-step codebase improvement.
- [`release`](./skills/release/SKILL.md): prepare and validate releases.
- [`second-opinion`](./skills/second-opinion/SKILL.md): ask another local AI CLI to critique a proposal.

## Agent Templates

Reusable templates live in [`templates`](./templates/), grouped by category/tech.

- [`fullstack-js`](./templates/fullstack-js/AGENTS.md): `AGENTS.md` template for TypeScript full-stack web apps with React UI, shadcn component conventions, Drizzle schemas/migrations, and separated `src/components`, `src/lib`, and `src/server` ownership.
