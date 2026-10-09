# Initial service objectives

These are targets pending evidence, not contractual guarantees.

- Platform availability: 99.5% monthly excluding agreed maintenance.
- Supported automated first-response median: under 30 seconds measured from verified inbound ingestion.
- Incident detection: alert on repeated webhook auth failures, stalled queues and outbound delivery errors.
- Human escalation: target 95% successfully routed valid requests.
- No tolerated confirmed cross-tenant disclosure or unauthorized privileged tool execution.

Instrument per-provider latency and failures separately; dependency outages must not be silently counted as successful automation. Review targets after live pilots and publish contractual SLA only with support and recovery capacity.
