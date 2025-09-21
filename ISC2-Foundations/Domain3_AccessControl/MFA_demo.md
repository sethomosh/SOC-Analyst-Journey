# MFA Demo — quick guide

## objective
show how to enable MFA on common platforms and document screenshots.

## github (free)
1. settings -> security -> two-factor authentication -> enable -> use authenticator app or sms
2. screenshot of 2fa enabled page

## azure ad (recommended)
1. azure portal -> azure ad -> security -> multifactor authentication -> enable for users or conditional access policy
2. enable conditional access: require MFA for external access or privileged roles
3. screenshot of conditional access policy & user enabled

## google workspace / other
- similar flow: security -> 2-step verification

## evidence to include
- `artifacts/mfa_github_enabled.png`
- `artifacts/mfa_azure_policy.png`
- note: redact any personal MFA codes/screenshots that reveal secrets

