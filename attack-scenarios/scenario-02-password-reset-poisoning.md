# Scenario 02: Password Reset Poisoning

## Objective
Test whether Host Header Injection can influence password reset functionality, enabling an attacker to poison reset URLs.

## Steps
1. Capture a password reset request.
2. Modify the `Host` header to an attacker-controlled domain.
3. Replay the request and inspect any generated reset links or server behavior.

## Expected Outcome
Reset functionality should enforce the legitimate host and never generate links or actions for attacker-controlled domains.

## Findings
- The password reset logic was influenced by the manipulated host header.
- This could allow attackers to redirect reset links or perform reset poisoning.

## Evidence
- `screenshots/password-reset-poisoning.png`
