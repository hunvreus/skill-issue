---
name: investigate
description: "Investigate live or deployed-app issues by gathering evidence from health checks, logs, metrics, deploy history, config, and remote hosts. Use when the problem is happening outside the local dev loop: production, staging, a server, Cloudflare, VPS, CI/CD runtime, logs, alerts, or deployed behavior."
---

# Investigate

## Workflow

1. **Pin down the symptom**. What is broken, since when, who is affected, and what changed (deploys, config, dependencies).
2. **Name the targets**. Environment, platform or host, service, and deployed version.
3. **Gather read-only evidence**. Health endpoints, logs, metrics, recent deploys, config, resource usage.
4. **Recommend a path**. Separate immediate mitigation (including rollback) from the root-cause fix.
5. **Close knowledge gaps**. If the investigation surfaced missing operator knowledge, update `docs/development/`.

## Guardrails

- If the issue reproduces locally, debug it locally instead.
- Read-only by default. Restarts, migrations, DNS or firewall changes, deletes, and any other production mutation need explicit approval.
- Bound every command with timeouts, line limits, or time windows; do not dump huge logs.
- Do not expose secrets from env files, logs, or dashboards.
- Label what the evidence confirms versus what is still a hypothesis.
