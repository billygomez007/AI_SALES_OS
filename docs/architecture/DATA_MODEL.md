# Logical data model

## Identity
Organization(id, name, market, timezone, currency); User(id, email, mfa); Membership(user_id, organization_id, role); Session; AuditEvent.

## Channels
ChannelConnection(id, organization_id, provider, encrypted_secret_ref, status); ChannelIdentity(id, organization_id, external_id); WebhookEvent(id, provider_event_id, organization_id, payload_hash, received_at, processed_at).

## Sales
Contact(id, organization_id, consent_status); Conversation(id, organization_id, channel_connection_id, contact_id, state); Message(id, organization_id, conversation_id, direction, provider_message_id, delivery_state); Lead(id, organization_id, contact_id, stage, owner_id, source); Deal; Appointment.

## AI
Agent(id, organization_id, active_version_id, mode); AgentVersion(id, agent_id, policy, knowledge_version); KnowledgeSource; KnowledgeChunk(organization_id, embedding); ToolExecution(id, organization_id, action, approval_state, idempotency_key); EvaluationRun.

## Billing
Plan; Subscription(organization_id, status); UsageLedger(organization_id, unit, quantity, provider_cost, billable_amount); Invoice.

## Constraints
Unique (provider, provider_event_id); unique scoped external identity; foreign keys across rows require organization match; tenant filtering mandatory; timestamps UTC; currency values in integer minor units; immutable audit entries; lifecycle states explicit.

## Retention
Store only necessary message and contact data according to purpose, consent, contracts and market requirements. Support deletion and access requests while preserving legally required financial records.
