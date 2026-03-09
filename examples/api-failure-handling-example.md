# API Failure Handling Example

## Scenario

An automation sends data to a third-party enrichment API.

## Failure classes

### Retryable
- timeout
- rate limit
- temporary 5xx response

### Non-retryable
- invalid API key
- malformed request
- missing required fields

## Response strategy

- retry retryable failures with backoff
- stop immediately on non-retryable failures
- log failure type
- alert if failure rate crosses threshold
