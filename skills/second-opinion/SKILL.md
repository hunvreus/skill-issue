---
name: second-opinion
description: Ask another local AI CLI for feedback on a proposal, architecture, feature plan, refactor, review, or technical decision, then compare the feedback and produce a revised assessment. Use when the user wants another model's opinion or asks to check a plan with Gemini, Claude, Codex, Cursor, or another installed AI tool.
---

# Second Opinion

## Workflow

1. **Pick the CLI**. Use the one the user named. Otherwise detect candidates with `command -v` (`claude`, `gemini`, `codex`, `cursor-agent`, `opencode`, `aider`) and ask which to use.
2. **Check invocation**. Read the CLI's `--help` for its non-interactive prompt mode and any read-only or sandbox flag. Avoid modes that open editors, edit files, install packages, or start sessions.
3. **Write the proposal**. In a `mktemp -d` directory, write `proposal.md` with the proposal, constraints, and specific questions: critique, missed risks, alternatives.
4. **Ask**. Run the CLI on the proposal and save the raw response as `feedback.md` in the same directory. On failure, report the command and error.
5. **Weigh it**. Adopt what holds up, reject what does not, and say why.

## Output

- CLI used, proposal and feedback paths
- Points adopted and points rejected
- Revised assessment or proposal

## Guardrails

- Only run a CLI the user named or approved; it may be paid or networked.
- Send the proposal and the context it needs, not the repo. Never send secrets, credentials, or customer data.
- The other AI must not modify the repo.
- Treat the feedback as advisory, not authoritative.
