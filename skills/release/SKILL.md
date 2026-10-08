---
name: release
description: Prepare, validate, document, tag, or publish a software release. Use when the user asks to cut a release, prepare release notes, update changelog, bump a version, create a tag, or validate release readiness.
---

# Release

## Workflow

1. **Identify the target**. Version, branch or package, and whether this is a dry run or a publish.
2. **Review changes**. Commits, PRs, and changelog entries since the last tag.
3. **Validate**. Tests, typecheck, build, packaging, and migrations as relevant.
4. **Bump consistently**. Update every place the version must agree: manifests, lockfiles, changelog, generated metadata. The tag matches the version: `2.0.2` → `v2.0.2`.
5. **Draft notes**. Changelog and release notes in the repo's existing format.
6. **Stop before publishing**. Summarize version, tag, validation results, changed files, and the notes draft.
7. **Publish on approval**. Tag, push, and publish per repo conventions.

## Guardrails

- Get explicit approval before creating or pushing tags, pushing release commits, publishing, or deploying.
- Do not guess the version bump or release notes format; infer from repo conventions or ask.
- Report failed or skipped checks; never hide them.
