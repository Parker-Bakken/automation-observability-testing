# Automation Testing Checklist

Use this checklist before moving any workflow to production.

## 1. Trigger validation
- Confirm the workflow triggers under the expected conditions
- Confirm duplicate triggers are handled safely
- Confirm invalid triggers are rejected or ignored

## 2. Input validation
- Required fields are checked
- Empty values are handled
- Incorrect data types are rejected
- Unexpected payload keys do not break processing

## 3. Happy path testing
- Workflow completes successfully with correct sample data
- Outputs are correct and complete
- Side effects match expectations

## 4. Failure path testing
- API timeout scenario tested
- API 4xx scenario tested
- API 5xx scenario tested
- Missing credential scenario tested
- Malformed input scenario tested
- Dependency unavailable scenario tested

## 5. Retry behavior
- Retries occur only for retryable failures
- Retries do not create duplicates
- Retry limits are enforced
- Retry outcomes are logged

## 6. Data integrity
- Duplicate rows are prevented
- Idempotency strategy is defined
- Partial writes are detected
- Rollback or cleanup path exists where needed

## 7. Alerts and logs
- Failures create usable logs
- Alert destination is configured
- Alert includes workflow name, error summary, and run ID

## 8. Operational readiness
- Owner is assigned
- Recovery steps are documented
- Known limitations are documented
- Deployment checklist is complete

## Approval rule

A workflow is not production-ready because it works once.
It is production-ready when it behaves predictably across normal, bad, and failing conditions.
