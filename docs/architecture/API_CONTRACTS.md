# API contracts (draft v1)

## General
HTTPS JSON APIs; session or scoped bearer authentication; version path /v1; request_id; consistent error {code,message,request_id}; cursor pagination; validation and rate limits. All mutations re-check authenticated organization membership.

## Endpoints
GET /v1/me; POST /v1/organizations; GET /v1/conversations; GET /v1/conversations/{id}/messages; POST /v1/conversations/{id}/takeover; POST /v1/conversations/{id}/reply; GET /v1/leads; POST /v1/leads; PATCH /v1/leads/{id}; POST /v1/agents; POST /v1/agents/{id}/versions; POST /v1/agents/{id}/publish; GET /v1/appointments; POST /v1/appointments; GET /v1/usage; POST /v1/channels/whatsapp/webhook.

## Webhook acceptance
Confirm provider challenge via configured verification token where applicable. For events verify HMAC/signature on raw body, guard time/replay where provider supports it, persist and acknowledge quickly; process asynchronously.

## Tool contract example
propose_appointment({lead_id,calendar_id,start_at,timezone}); server verifies availability and returns proposal, NOT a confirmed booking. confirm_appointment requires authorized request and idempotency key.

## Idempotency
Required on customer-visible mutations and payment-link issuance. Retried requests return the original result, not duplicate actions.
