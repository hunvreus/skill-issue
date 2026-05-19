---
name: investigate
description: "Investigate live or deployed-app issues by gathering evidence from health checks, logs, metrics, deploy history, config, and remote hosts. Use when the problem is happening outside the local dev loop: production, staging, a server, Cloudflare, VPS, CI/CD runtime, logs, alerts, or deployed behavior."
---

# Investigate Live

## Scope

- A live or deployed app, environment, host, service, incident, symptom, alert, or user-reported production issue.
- If the affected target is unclear, identify environment, host/platform, timeframe, and symptom before running commands.

## Workflow

1. **Define symptom**. Capture what is broken, when it started, who is affected, and what changed recently.
2. **Map targets**. Identify platform, environment, host/service names, deploy version, domains, databases, queues, and dependencies.
3. **Gather read-only evidence**. Check health endpoints, logs, metrics, recent deploys, config, resource usage, errors, and dependency status.
4. **Form hypotheses**. List likely causes and test one at a time.
5. **Use bounded commands**. Prefer targeted commands with timeouts and limited output; avoid dumping secrets or huge logs.
6. **Recommend fix path**. Separate immediate mitigation, root-cause fix, rollback, and follow-up hardening.
7. **Document findings**. Update `docs/devops.md` or a runbook if the investigation reveals missing operational knowledge.

## Output

- Symptom and affected scope
- Evidence gathered
- Most likely cause
- Immediate mitigation
- Root-cause fix or next diagnostic step
- Docs/runbook gaps

## Guardrails

- Use `debug` instead when the issue can be reproduced locally with tests, scripts, or a dev server.
- Start read-only; do not restart services, run migrations, change DNS, or mutate production without explicit approval.
- Do not expose secrets from logs, env files, dashboards, or command output.
- Distinguish facts from hypotheses.
- Keep remote targets explicit and commands bounded.
