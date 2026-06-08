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
- Prefer this body shape:

```md
# Verb

## Input
## Workflow
## Output
## Examples
## Guardrails
```

- `Examples` is optional. Use it only when examples clarify categories or materially improve behavior.
- Update `README.md` when adding, removing, or renaming skills.
- Keep `agents/openai.yaml` aligned with the skill.

## Templates

- Reusable templates belong under `templates/<category-tech>/`.
- Template bundles can include `AGENTS.md` and related starter files.
- Use descriptive category/tech directory names such as `fullstack-js`.
