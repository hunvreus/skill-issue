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
4. **Handle versioning**. If the version changes, update package manifests, lockfiles, changelogs, and generated metadata that must stay consistent.
5. **Align tag and version**. Keep the release version aligned with the git tag, such as version `2.0.2` and tag `v2.0.2`.
6. **Update release docs**. Prepare changelog, release notes, migration notes, and known issues. If the release notes format is unclear, ask instead of inventing one.
7. **Summarize before publishing**. Report branch, target version, tag, validation results, changed files, and release notes draft.
8. **Create release artifact**. Tag, package, publish, or open the release only according to repo conventions and explicit user approval.
9. **Report outcome**. Include version, artifacts, validation, skipped checks, and follow-up tasks.

## Output

- Release target and scope
- Matching version and tag
- Changelog or release notes
- Validation run
- Version/tag/artifact status
- Known issues and follow-up work

## Guardrails

- Do not create or push tags, publish releases, push release commits, or deploy without explicit user approval.
- Do not invent semantic version bumps; infer from repo rules or ask.
- Do not invent release notes format; infer from repo rules or ask.
- Do not hide failed or skipped validation.
- Preserve existing release conventions over generic release process.
