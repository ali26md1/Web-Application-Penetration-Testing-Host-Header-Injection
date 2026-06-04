# Scenario 05: Validation Bypass Testing

## Objective
Evaluate the application’s input validation and how malformed or unexpected header values are handled.

## Steps
1. Intercept a request with Burp Suite.
2. Introduce non-standard or malformed host-related header values.
3. Replay the request and observe whether the server rejects or accepts the malformed headers.

## Expected Outcome
The application should validate and sanitize all host-related headers, rejecting malformed or unexpected values.

## Findings
- Host header validation was insufficient in the tested environment.
- Malformed or unexpected values may bypass controls and lead to injection or routing issues.
