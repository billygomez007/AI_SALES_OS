# Disaster recovery

## Objectives (initial planning)
Proposed RPO 24 hours and RTO 8 hours for noncritical pilot service, subject to measured customer need and provider capabilities. Production SLO commitments must be validated by drills.

## Protections
Encrypted database backups and point-in-time recovery where available; off-site storage; versioned deployment artifacts; secrets recovery procedures; infrastructure configuration in code.

## Exercise
Quarterly sandbox restoration; compare tenant record counts, authorization policies, attachments, critical ledgers and delivery state integrity. Test restoring with a compromised key rotated.

## Procedure
Declare incident, stop high-risk sending, identify last-good recovery point, restore into isolated environment, validate data and ownership, obtain incident commander approval, redirect traffic, monitor, reconcile delayed events and produce postmortem.
