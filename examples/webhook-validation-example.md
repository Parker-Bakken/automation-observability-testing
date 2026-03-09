# Webhook Validation Example

## Scenario

A webhook receives inbound lead data from a form tool and forwards it into a CRM and Slack notification flow.

## Risk

If required fields are missing or malformed, the workflow may fail downstream or create incomplete records.

## Validation rules

Required:
- email
- source
- submitted_at

Optional:
- first_name
- company
- phone

## Testing cases

### Valid payload
Expected result:
- workflow continues
- CRM record created
- Slack notification sent

### Missing email
Expected result:
- workflow stops
- validation error logged
- alert sent if threshold exceeded

### Invalid timestamp
Expected result:
- workflow rejects payload
- error includes payload ID
- no downstream actions occur

## Observability notes

Log:
- payload receipt timestamp
- validation result
- reason for rejection
- downstream execution status
