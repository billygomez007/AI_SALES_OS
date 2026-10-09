# Operational runbook

## Daily
Check webhook failure rate, queue depth, conversation delivery lag, cost anomalies, AI error budgets, appointment confirmations, tenant-level rate limits and platform health.

## Incident severity
SEV-1 data exposure, cross-tenant access, unauthorized payments or total outage; immediate containment/escalation. SEV-2 partial delivery or elevated AI errors; assign incident lead and mitigations. SEV-3 isolated customer defect; tracked remediation.

## AI failure
Pause affected agent or switch to human-only mode. Preserve minimized evaluation evidence. Disable faulty tool or provider, investigate and regression-test before reactivation.

## Channel outage
Throttle retries, deduplicate, alert clients, show status in inbox, and allow human routing where supported.

## Secret compromise
Revoke and rotate, inspect access logs, invalidate affected sessions/connections, assess exfiltration and notify according to obligations.

## Deployment
Review migration plan, backup, CI, feature flags, staged release, smoke checks and tested rollback. Do not run destructive production migrations casually.
