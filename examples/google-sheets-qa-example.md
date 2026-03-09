# Google Sheets QA Example

## Scenario

A content pipeline writes approved short-form content ideas into Google Sheets.

## Risks

- duplicate rows
- blank fields
- malformed publish dates
- status drift between workflow steps

## QA controls

- require unique content ID
- validate title is not blank
- validate status is one of:
  - idea
  - approved
  - queued
  - published
- validate publish date format before write

## Failure handling

If row insert fails:
- log content ID
- retry if transient
- alert if retries exhausted

If duplicate detected:
- skip insert
- log duplicate event
- avoid double-processing
