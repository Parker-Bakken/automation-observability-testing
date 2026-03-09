# Retry and Fallback Patterns

## Retry only when appropriate

Retries are useful for:
- network instability
- temporary API timeouts
- rate limits
- brief service outages

Retries are dangerous for:
- invalid payloads
- authentication misconfiguration
- permanent 4xx errors
- duplicate-creating operations without idempotency protection

## Recommended retry rules

### Exponential backoff
Retry after increasing delays rather than instantly retrying.

### Retry caps
Set a maximum retry count to avoid infinite loops.

### Idempotency protection
Ensure repeated attempts do not create duplicate side effects.

### Clear logging
Each retry should log:
- attempt number
- cause
- delay
- final outcome

## Fallback strategies

### Manual review queue
Send failed items to a queue for human review.

### Secondary notification path
If Slack alerting fails, send email or log to a backup system.

### Safe skip
Skip non-critical enrichment steps while allowing core workflow completion.

### Dead-letter handling
Store unprocessable records for later review rather than losing them silently.
