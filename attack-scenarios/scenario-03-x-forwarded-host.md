# Scenario 03: X-Forwarded-Host Manipulation

## Objective
Evaluate whether the application trusts `X-Forwarded-Host` values and how it impacts request handling.

## Steps
1. Intercept an HTTP request with Burp Suite.
2. Add or modify the `X-Forwarded-Host` header to a different domain.
3. Replay the request and observe application behavior.

## Expected Outcome
The application should ignore untrusted forwarded host headers or strictly validate them against the expected host.

## Findings
- `X-Forwarded-Host` was accepted by the application in this testing environment.
- This can lead to header trust issues, reverse proxy confusion, or bypasses in protected logic.

## Evidence
- `screenshots/x-forwarded-host.png`
