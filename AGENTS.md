# Agent Rules

## Communication

- Keep responses concise, technical, and direct.
- State uncertainty and scope limits explicitly.

## Repository

- This repo contains reusable agent skills and agent instruction templates.
- Keep skills concise, composable, and focused on just-in-time engineering workflows.
- Do not add app-specific framework rules to the root `AGENTS.md`.

## Skills

- Each skill lives in `skills/<name>/`.
- Keep `SKILL.md` frontmatter to `name` and `description`.
- Prefer the body shape documented in `README.md`: `Scope`, `Workflow`, `Output`, optional `Examples`, `Guardrails`.
- Update `README.md` when adding, removing, or renaming skills.
- Keep `agents/openai.yaml` aligned with the skill.

## Templates

- Reusable `AGENTS.md` templates belong under `templates/agents/`.
- Template files must not be named `AGENTS.md`; use descriptive inert names such as `js-react-fullstack.md`.
