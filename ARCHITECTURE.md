# System architecture

## Architecture style
Modular TypeScript monolith with an independently scaled async worker initially; extract services only when measurable scaling or isolation demands it.

## Components
Next.js SaaS UI and agency console; Node TypeScript API; PostgreSQL/Prisma; Redis/BullMQ workers; S3-compatible encrypted media; tenant-scoped retrieval using pgvector; realtime inbox transport; managed observability.

## Inbound lifecycle
1. Validate provider signature and timestamp.
2. Save immutable idempotent inbound event.
3. Resolve authorized channel connection and organization.
4. Normalize to message and enqueue AI work.
5. Load bounded tenant-approved knowledge and conversation context.
6. Ask model for response or allowlisted tool request.
7. Validate typed action, permissions, budgets, consent and business invariants in server code.
8. Persist outbound event then deliver with retry/backoff.
9. Write audit and usage ledger entries.

## Boundaries
AI output is untrusted. AI never gets database credentials, arbitrary SQL, shell, unrestricted web access or credentials. Provider adapters own verification and retries. Domain services own business invariants.

## Data separation
Every tenant-owned row has organization_id. Every API query must use authenticated membership scope. PostgreSQL row-level security may add a defense layer; never rely on UI filtering.

## Failure behavior
Deduplicate inbound events, use transactional outbox for externally visible actions, dead-letter exhausted jobs, and switch to human escalation if model or knowledge retrieval is unavailable.

See docs/architecture/ for data model, integration contracts and architectural rules.
