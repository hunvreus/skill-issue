---
name: deploy
description: Set up, validate, or run deployment for the current app on Cloudflare, a VPS, or both. Use when the user asks to deploy, configure deployment or CI/CD, choose a deploy target, or fix deployment readiness.
---

# Deploy

## Workflow

1. **Start from what exists**. Read deploy docs, CI/CD, Dockerfiles, platform config, and package scripts. Extend the existing path rather than replacing it.
2. **Propose before building**. If there is no deploy path, agree on target (Cloudflare, VPS, or Cloudflare in front of a VPS), environments, secrets, database/migrations, health check, and rollback before writing config.
3. **Make it repeatable**. Prefer CI/CD over one-off manual commands.
4. **Validate**. Use what is available: build, dry run, smoke test, health check, logs.
5. **Document**. Keep developer and operator notes under `docs/development/`, such as `deployment.md` or `environment.md`.

## Output

- Required secrets and env vars
- Deploy path (CI/CD or manual) and rollback path
- Validation run and anything skipped

## Guardrails

- Get explicit approval before deploying, mutating production, changing DNS, or running production migrations.
- Never print or commit secrets.
- Check current platform docs or a platform skill for platform specifics instead of relying on memory.
- On remote hosts, name the target explicitly and start with read-only probes.
