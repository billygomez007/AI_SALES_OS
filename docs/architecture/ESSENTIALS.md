# Architecture essentials

Non-negotiables: organization_id ownership on tenant data; authenticated membership resolution; default-deny scopes; signed webhooks; transactional outbox; idempotent external operations; request and per-tenant AI budgets; per-tenant retrieval isolation; privacy-safe observability; approval gates for high-impact tools.

Never allow a model to execute SQL or generate direct external API calls with bearer credentials. All model actions must pass through schema-validated domain tools. Use server-side event state machines for channel delivery and appointments. Keep usage ledger append-only with corrections, not silent rewrites.
