# Scenario 04: Duplicate Host Header Testing

## Objective
Test how the application handles multiple `Host` headers in the same request.

## Steps
1. Intercept a request in Burp Suite.
2. Add a second `Host` header with a different value.
3. Forward the request and inspect how the server handles the duplicate header.

## Expected result
The server should reject duplicate `Host` headers and preserve a single trusted host value.

## Findings
- The application behaved inconsistently with duplicate `Host` headers.
- This opens the door for attackers to exploit header parsing ambiguity.

## Evidence
- `screenshots/host-header-manipulation.png`
