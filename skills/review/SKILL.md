---
name: review
description: Review code changes or a selected code scope for correctness, regressions, missing tests, security risks, dependency risks, product mismatch, and mismatch with the requested behavior. Use when the user asks for a code review, PR review, branch review, diff review, security review, or review since a commit.
---

# Review

## Input

- A PR, branch, commit range, diff, file list, feature scope, or review category.
- Use explicit input first; otherwise infer from context, recent edits, selected files, or branch.
- Safest default: review current changes for correctness, regressions, tests, security, dependencies, product mismatch, and operational risk.

## Workflow

1. **Identify input**. Determine whether the review target is a PR, branch, commit range, diff, files, or current worktree.
2. **Read context**. Check relevant specs, issues, `AGENTS.md`, docs, tests, and config that define expected behavior or standards.
3. **Inspect changes**. Review for correctness, regressions, missing tests, security risks, dependency risks, error handling gaps, operational risk, and product/spec mismatch.
4. **Prioritize findings**. Report actionable issues first, ordered by severity, with file and line references when possible.
5. **Separate uncertainty**. List open questions, assumptions, and residual risks after findings.
6. **Report only**. Do not edit code unless the user explicitly asks for fixes.

## Output

- Findings first, ordered by severity
- File and line references when possible
- Open questions and assumptions
- Test gaps or unchecked risks
- Brief summary only after findings

## Examples

- Code review: correctness, regressions, maintainability, tests.
- Security review: auth, authorization, input handling, secrets, injection, SSRF, tenant isolation.
- Dependency review: vulnerable packages, license or supply-chain risk, unnecessary new dependencies.
- Product review: behavior mismatch, missing edge cases, confusing UX, acceptance criteria gaps.
- Operational review: deploy risk, migrations, rollback, observability, config, data safety.

## Guardrails

- Prioritize real bugs and behavioral risks over style preferences.
- Do not report issues already enforced by passing tooling unless the tooling coverage is itself the issue.
- If no issues are found, say so directly and mention any test gaps or unchecked risks.
- Keep summaries secondary to findings.
