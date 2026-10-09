# AI safety design

## Threats
Prompt injection, adversarial user inputs, malicious knowledge documents, hallucinated pricing/availability, identity conflation, model extraction, unauthorized tool invocation, excessive spend and unconsented outreach.

## Controls
System-owned policies; narrow tenant-scoped retrieval; typed allowlisted tools; explicit preconditions; business fact citations in internal evaluation; PII minimization; rate and token budgets; dual approval for sensitive effects; fallback to human agents.

## Evaluation sets
Correct inventory queries; unavailable product; ambiguous contact; fabricated discount; unverified payment; multilingual/noisy phrasing; instructions embedded in uploaded documents; cross-tenant record attempts; duplicate booking/callback.

## Agent governance
Version policies and knowledge snapshots; staging simulation; owner approval for publish; incident kill switch; retention and consent checks applied independently of model output.
