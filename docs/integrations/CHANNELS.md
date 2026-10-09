# Messaging and voice channels

## WhatsApp (P0)
Use official WhatsApp Business Platform via an eligible account. Implement provider-specific challenge verification, signature validation, template/consent and service-window rules, message status callbacks and per-market delivery charges. Never use unofficial session scraping.

## Website widget (P0)
Signed widget configuration with domain allowlist, anonymous session rate limits, abuse defenses and optional customer identity verification.

## Instagram and Facebook (P1)
Use permitted Meta APIs, scoped permissions, app review and channel-specific rate limits. Feature availability depends on account eligibility.

## Voice (P2)
Use supported telecom/voice AI providers. Clarify caller disclosure, consent/recording, telephony regulation, emergency escalation and local language evaluation before launch.

## Shared adapter contract
verify(event), normalize(event), send(message), parseDeliveryReceipt(event), capabilities(connection); normalized records always retain provider metadata and tenant identity.
