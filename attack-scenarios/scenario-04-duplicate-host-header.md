# Scenario 04: Duplicate Host Header Testing

## Objective
Test application behavior when multiple `Host` headers are sent in a single HTTP request.

## Steps
1. Intercept a request in Burp Suite.
2. Add a second `Host` header with a different value.
3. Forward the request and inspect how the server handles the duplicate header.

## Expected Outcome
The server should reject duplicate `Host` headers and maintain a single trusted host value.

## Findings
- The application exhibited inconsistent behavior when duplicate `Host` headers were present.
- This can allow attackers to exploit header parsing ambiguities for bypasses or poisoning.

## Evidence
- `screenshots/host-header-manipulation.png`
