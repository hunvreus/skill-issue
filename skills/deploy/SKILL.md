---
name: deploy
description: Set up, validate, or run deployment for the current app on Cloudflare, a VPS, or a mixed architecture. Use when the user asks to deploy an app, configure deployment, set up CI/CD, choose a deployment target, document deployment, or fix deployment readiness.
---

# Deploy

## Input

- An app or service in the current repo, plus a target such as Cloudflare, VPS, or a mix of both.
- Use explicit input first; otherwise infer from context, config, docs, selected files, or branch.
- Safest default: define and document the deploy path before automating it.

## Workflow

1. **Inspect the app**. Identify runtime, build command, start command, ports, env vars, storage, database, background jobs, and health checks.
2. **Detect deploy path**. Read existing deploy docs, CI/CD, Dockerfiles, platform config, infra files, and package scripts.
3. **Choose route**. Use Cloudflare, VPS, or mixed deployment based on app needs and user preference.
4. **Plan setup if missing**. Confirm target, domain/DNS, environments, secrets, build, runtime, database/migrations, logs, monitoring, backups, rollback, and CI/CD trigger.
5. **Apply best practices**. Prefer least-privilege secrets, HTTPS, non-root processes where applicable, firewall or platform access controls, health checks, logs, rollback path, and documented env vars.
6. **Configure deployment**. Add or update platform config, CI/CD, Docker/systemd/service files, scripts, and docs using repo conventions.
7. **Validate**. Run local checks, build, deploy dry run where available, smoke test, health check, logs check, and rollback notes.
8. **Document**. Keep internal developer and operator deployment notes under `docs/development/`, such as `docs/development/deployment.md`, `docs/development/ci.md`, `docs/development/operations.md`, or `docs/development/environment.md`.

## Output

- Target and route chosen
- Config changed
- Secrets/env vars required
- CI/CD or manual deploy path
- Validation run
- Rollback and follow-up tasks

## Examples

- Cloudflare: Workers, Pages, DNS, routes, bindings, secrets, queues, D1, R2, KV, Durable Objects.
- VPS: SSH target, Docker or systemd, reverse proxy, firewall, TLS, logs, backups, restart policy.
- Mixed: Cloudflare DNS/proxy/access in front of a VPS app, or Workers edge in front of an origin service.

## Guardrails

- Do not deploy, mutate production, or change DNS without explicit user approval.
- Do not print or commit secrets.
- Do not assume platform-specific behavior; use official docs or available skills/tools for current platform details.
- For remote commands, resolve targets explicitly, prefer read-only probes first, and treat service restarts, migrations, DNS, firewall, and deletes as high-risk.
- If CI/CD is feasible, prefer repeatable deploys over one-off manual commands.
