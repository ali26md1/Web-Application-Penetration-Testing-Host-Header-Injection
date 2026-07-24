# Scenario 02: Password Reset Poisoning

## Objective
Verify whether Host Header Injection can affect password reset flows and cause reset links to point to an attacker-controlled domain.

## Steps
1. Capture a password reset request.
2. Modify the `Host` header to an attacker-controlled domain.
3. Replay the request and inspect any generated reset links or server behavior.

## Expected result
The password reset process should enforce the legitimate host and not build reset links from manipulated host input.

## Findings
- The password reset flow was affected by the manipulated `Host` header.
- This behavior could allow an attacker to poison reset URLs or redirect reset emails.

## Evidence
- `screenshots/password-reset-poisoning.png`
