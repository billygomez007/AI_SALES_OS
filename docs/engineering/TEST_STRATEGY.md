# Test strategy

## Unit
Organization access policy, pricing arithmetic, conversation state transitions, template rules, time zones, consent, prompt/tool argument parsing.

## Integration
Webhook signature and retry; tenant-scoped database transactions; model orchestration stubs; CRM/appointment flow; usage ledger consistency; provider callback errors.

## End to end
Business connects channel, publishes supervised agent, customer asks verified inventory question, lead captured, staff takes over, booking confirmed, analytics recorded.

## Security regression
Cross-tenant IDOR, prompt injection, malicious document RAG, replay, forged provider events, insecure tool call, rate-limit abuse, deletion requests and sensitive log scrubbing.

## Release protocol
Run automated tests; stage with synthetic data; document manual signoff; backup/migration readiness; canary rollout; rollback procedure; post-deploy smoke checks.
