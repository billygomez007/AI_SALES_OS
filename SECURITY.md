# Security policy

## Vulnerability reporting
Do not publish exploit details or credentials in public issues. Report privately to repository administrators via GitHub's private vulnerability reporting if configured; otherwise request a private reporting channel before sharing sensitive details.

## Minimum controls
MFA for privileged roles, strong authentication, default-deny RBAC, organization-scoped access checks and audit logs; TLS in transit and encrypted managed storage; least-privilege provider scopes, managed secrets, key rotation and egress restrictions.

## Webhooks and jobs
Validate provider signatures with raw request body, defend against replay, enforce idempotency keys, bound payload sizes, authenticate internal job producers and record delivery outcomes.

## AI safety
Treat user prompts, retrieved pages and uploaded files as hostile; allowlist tools; validate tool inputs; prevent cross-tenant retrieval; gate payments, refunds, pricing changes and mass messaging behind approvals.

## Customer data
Consent and legal-basis records, deletion/export workflows, data minimization, configurable retention, redacted logs, processor inventory and documented breach process. Never place secrets or raw customer data in issues, traces, public prompts or fixtures.

## Release gates
Threat-model review, dependency checks, tenant-isolation tests, webhook forgery/replay tests, prompt-injection tests, authorization review, backups and restoration rehearsal before production.

## Incident process
Contain, revoke compromised credentials, preserve minimal audit evidence, assess impact, notify responsible persons and meet jurisdiction-specific legal obligations. See docs/operations/RUNBOOK.md.
