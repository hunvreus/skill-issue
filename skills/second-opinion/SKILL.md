---
name: second-opinion
description: Ask another local AI CLI for feedback on a proposal, architecture, feature plan, refactor, review, or technical decision, then compare the feedback and produce a revised assessment. Use when the user wants another model's opinion or asks to check a plan with Gemini, Claude, Codex, Cursor, or another installed AI tool.
---

# Second Opinion

## Scope

- A proposal, architecture, feature plan, refactor plan, implementation approach, review finding, or technical decision to sanity-check.
- The target AI should be specified by the user or clear from context.
- If no target AI is specified, detect available local AI CLIs and ask the user which one to use.

## Workflow

1. **Clarify target and scope**. Identify the proposal to review and the AI CLI to ask. If either is missing, infer from context or ask one focused question.
2. **Detect available CLIs**. Check likely commands with `command -v`, such as `claude`, `gemini`, `codex`, `cursor`, `opencode`, and `aider`. Do not assume a CLI exists.
3. **Verify invocation**. Use the selected CLI's help output before running it. Prefer non-interactive prompt modes and avoid commands that open editors, mutate files, install packages, or start long-lived sessions.
4. **Write the proposal**. Create a temporary directory with `mktemp -d` and write the proposal, relevant constraints, and explicit questions to a file such as `proposal.md`.
5. **Ask the other AI**. Pass the proposal file content to the selected CLI. Ask for critique, missed risks, alternatives, and concrete changes to the proposal.
6. **Capture feedback**. Save the raw response in the same temporary directory. If the CLI fails, report the command, failure mode, and closest safe fallback.
7. **Compare judgments**. Separate useful objections from weak or irrelevant feedback. Do not accept the other AI's answer just because it came from another model.
8. **Revise if warranted**. Produce a final assessment, noting what changed, what did not, and why.

## Output

- Target AI and CLI used
- Proposal file path and feedback file path
- Other AI's strongest points
- Points rejected or deprioritized
- Final assessment
- Revised proposal when useful

## Examples

- `second-opinion with gemini on this architecture plan`
- `ask Claude for a second opinion on the refactor`
- `get another model to critique this feature proposal`
- `compare our deploy plan with Codex`

## Guardrails

- Do not send secrets, credentials, private keys, tokens, customer data, or unnecessary proprietary context to another CLI.
- Do not run a paid, networked, or external AI CLI unless the user requested that tool or approved it.
- Do not let the other AI mutate the repository; use it for feedback only.
- Keep the prompt focused. Send the proposal and constraints, not the entire repo, unless explicitly requested.
- Treat second opinions as advisory evidence, not authority.
