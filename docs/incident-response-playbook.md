# Incident Response Playbook

## Goal

Restore workflow reliability quickly, reduce business impact, and capture lessons for future prevention.

## Incident stages

### 1. Detect
Identify:
- what failed
- when it failed
- which workflows are affected
- whether the failure is ongoing

### 2. Triage
Classify impact:
- low: isolated failure, low urgency
- medium: repeated failures or delayed processing
- high: customer-facing, revenue-impacting, or system-wide failure

### 3. Contain
Prevent additional damage:
- pause workflow if needed
- disable failing branch
- stop duplicate processing
- switch to manual fallback

### 4. Diagnose
Review:
- execution logs
- payload samples
- recent changes
- external dependency health
- credential or auth issues

### 5. Resolve
Apply fix:
- correct logic
- patch credentials
- restore dependency
- replay failed jobs if safe

### 6. Document
Record:
- summary
- root cause
- impact
- timeline
- resolution
- preventive action items

## Post-incident questions

- Was the issue detected quickly enough?
- Were the logs sufficient?
- Was alerting effective?
- Was retry behavior correct?
- Can this class of failure be prevented in the future?
