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

## Workflow
## Output
## Guardrails
```

- Only encode what a strong model would not do by default: approval gates, personal conventions, or tool mechanics. Skip generic engineering method.
- `Output` is optional. Use it only when a specific report shape matters.
- Set `allow_implicit_invocation: false` in `agents/openai.yaml` for skills that should run only when explicitly requested.
- Update `README.md` when adding, removing, or renaming skills.
- Keep `agents/openai.yaml` aligned with the skill.

## Templates

- Reusable templates belong under `templates/<category-tech>/`.
- Template bundles can include `AGENTS.md` and related starter files.
- Use descriptive category/tech directory names such as `fullstack-js`.
