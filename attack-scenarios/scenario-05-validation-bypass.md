# Scenario 05: Validation Bypass Testing

## Objective
Evaluate how the application handles malformed or unexpected host-related header values.

## Steps
1. Intercept a request with Burp Suite.
2. Introduce non-standard or malformed host-related header values.
3. Replay the request and observe whether the server rejects or accepts the malformed headers.

## Expected result
The application should sanitize and reject malformed or untrusted host-related headers.

## Findings
- Host header validation was insufficient.
- Malformed or unexpected host headers may bypass controls and affect request handling.
