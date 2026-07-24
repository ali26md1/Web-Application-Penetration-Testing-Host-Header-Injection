# Scenario 03: X-Forwarded-Host Manipulation

## Objective
Check whether the application trusts `X-Forwarded-Host` values and whether that trust affects request handling.

## Steps
1. Intercept an HTTP request with Burp Suite.
2. Add or modify the `X-Forwarded-Host` header to a different domain.
3. Replay the request and observe application behavior.

## Expected result
The application should ignore untrusted forwarded host headers or validate them before using them in routing or URL generation.

## Findings
- `X-Forwarded-Host` was accepted by the application.
- This could cause proxy trust issues and let attackers influence request handling if that value is trusted.

## Evidence
- `screenshots/x-forwarded-host.png`
