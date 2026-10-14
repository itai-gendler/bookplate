---
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
---

# Security

The Security tab of Settings: changing the password and checking that the
server's email works.

## Boundary

Owns changing a known password and the test email. Does not own signing in,
resetting a forgotten password or deleting the account.
