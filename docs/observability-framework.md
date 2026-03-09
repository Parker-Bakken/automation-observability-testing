# Observability Framework for Automation Systems

## Purpose

Observability in automation means being able to quickly understand workflow behavior, detect failures, and diagnose root causes without guesswork.

## The five pillars

### 1. Run visibility
Every automation run should be traceable.
Track:
- workflow name
- execution ID
- trigger source
- timestamp
- status
- duration

### 2. Input visibility
Capture important incoming data:
- webhook payload summary
- record IDs
- source system
- user or event identifier

Do not log secrets or sensitive data unnecessarily.

### 3. Step-level status
Critical steps should expose:
- started
- completed
- failed
- skipped
- retried

### 4. Error context
Every failure should include:
- step name
- error message
- probable cause
- affected record or payload ID
- retry count

### 5. Alerting and escalation
Failures should trigger alerts based on severity.

Examples:
- low severity: log only
- medium severity: Slack alert
- high severity: Slack + email + manual intervention

## Minimum viable observability

For a workflow to be production-ready, it should have:
- unique run identifier
- execution log
- error capture
- failure alert
- retry policy
- manual recovery steps

## Questions observability should answer

- Did the workflow run?
- Did it complete?
- What data did it process?
- Where did it fail?
- Was the failure transient or systemic?
- Did retry resolve it?
- Does a human need to intervene?

## Final rule

If you cannot diagnose a failed workflow within a few minutes, your observability is too weak.
