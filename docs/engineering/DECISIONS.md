# Architecture decision records

## ADR-001 Modular monolith
Accepted initially for velocity, consistent authorization and low ops burden; workers are separately deployable. Revisit with demonstrated throughput or team boundaries.

## ADR-002 PostgreSQL system of record
Accepted for relational CRM integrity; use pgvector only with tenant-filtered retrieval.

## ADR-003 Official channel APIs
Accepted; avoid browser automation or unofficial WhatsApp scraping to reduce account, policy and reliability risks.

## ADR-004 Provider-neutral model interface
Accepted; compare quality/cost and allow failover under policy. Do not claim model interchangeability without regression tests.

## ADR-005 Human-governed high-risk actions
Accepted; irreversible financial and bulk communications actions require explicit approval and logged tool execution.
