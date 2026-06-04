# Scenario 01: Basic Host Header Manipulation

## Objective
Test how the application handles an altered `Host` header and whether it accepts or reflects the manipulated value.

## Steps
1. Intercept a request using Burp Suite Proxy.
2. Modify the `Host` header to a controlled domain, such as `attacker.com`.
3. Forward the request and inspect the application response.

## Expected Outcome
The application should reject unexpected host values and enforce the original host.

## Findings
- The application accepted the manipulated `Host` header in the request.
- The response indicated that host header validation was weak or absent.

## Evidence
- `screenshots/intercepted-request.png`
