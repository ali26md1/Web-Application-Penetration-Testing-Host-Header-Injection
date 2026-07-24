# Scenario 01: Basic Host Header Manipulation

## Objective
Check whether the application accepts a modified `Host` header and how it behaves when the host value is changed.

## Steps
1. Intercept a request using Burp Suite Proxy.
2. Modify the `Host` header to a controlled domain, such as `attacker.com`.
3. Forward the request and inspect the application response.

## Expected result
The target should reject unexpected host values and continue using the legitimate host.

## Findings
- The application accepted the modified `Host` header.
- The response showed that host header validation was either weak or not enforced.

## Evidence
- `screenshots/intercepted-request.png`
