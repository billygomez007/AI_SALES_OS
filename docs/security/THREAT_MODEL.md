# Threat model

## Assets
Customer messages, lead PII, channel tokens, model configuration, business pricing/catalog, payment records, tenant membership and audit/usage ledgers.

## Trust boundaries
External messaging providers -> public webhook -> tenant dispatcher -> queued worker -> retrieval -> model -> validated tool gateway -> domain database/provider APIs.

## Representative attacks / mitigations
Forged webhook: raw-body signature validation and replay window. Duplicate delivery: unique provider_event_id and idempotent processing. Tenant IDOR: membership-scope checks, composite keys and RLS tests. Malicious attachment: quarantine/scanning, size/type limits, no execution. Prompt injection: isolate untrusted content; allowlisted authorized actions. Model secrets leak: no secrets in prompts. Mass send abuse: quota and approval. Insider access: JIT audited support access. Billing manipulation: immutable usage ledger/reconciliation.

## Reviews
Update model after new channels, high-impact AI tools, payments and regional deployments. Track residual risks with owners and deadlines.
