---
name: release
description: Prepare, validate, document, tag, or publish a software release. Use when the user asks to cut a release, prepare release notes, update changelog, bump a version, create a tag, or validate release readiness.
---

# Release

## Scope

- A version, branch, package, changelog scope, release target, or request to prepare or validate a release.
- If the release target is unclear, identify the repo's release conventions before changing files.

## Workflow

1. **Identify release target**. Determine version, branch, package, environment, and whether this is a draft, dry run, or publish.
2. **Inspect changes**. Review commits, merged PRs, changelog entries, and user-facing changes since the previous release.
3. **Validate readiness**. Run relevant tests, typecheck, lint, build, packaging, migration, and smoke checks.
4. **Update release docs**. Prepare changelog, release notes, migration notes, and known issues.
5. **Handle versioning**. Bump version files and lockfiles only when the release process requires it.
6. **Create release artifact**. Tag, package, publish, or open the release according to repo conventions and user approval.
7. **Report outcome**. Include version, artifacts, validation, skipped checks, and follow-up tasks.

## Output

- Release target and scope
- Changelog or release notes
- Validation run
- Version/tag/artifact status
- Known issues and follow-up work

## Guardrails

- Do not publish, push tags, or deploy without explicit user approval.
- Do not invent semantic version bumps; infer from repo rules or ask.
- Do not hide failed or skipped validation.
- Preserve existing release conventions over generic release process.
