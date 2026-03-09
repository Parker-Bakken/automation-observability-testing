# Alerting Workflow Example

## Goal

Ensure automation owners know when production workflows fail.

## Alert trigger conditions

- workflow failed
- retry limit reached
- daily execution count drops below expected range
- duplicate error repeats more than 3 times in 1 hour

## Alert payload should include

- workflow name
- environment
- run ID
- timestamp
- failed step
- short error summary
- link to logs or execution history

## Severity routing

### Low
Log only

### Medium
Slack alert

### High
Slack + email + manual escalation
