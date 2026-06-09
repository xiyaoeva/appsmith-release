# A4 - Test Outline Draft

## Backend checks

- redaction removes sensitive keys.
- truncation keeps bounded payload size.
- GET history returns newest-first order.
- unauthorized users cannot read history.

## Frontend checks

- success run appends SUCCESS record.
- failed run appends FAILURE record.
- cancelled run appends CANCELLED record.
- opening History tab triggers fetch.

## E2E checks

- run twice and verify 2 rows.
- run one failing query and verify status+preview.
