---
appliesTo:
  - { type: capability, id: reset-password }
  - { type: capability, id: confirm-email-address }
references:
  - { kind: code, role: implementation, target: lib/auth.ts }
---

# Emailed reset and confirmation links work once, for an hour

A password reset link or an address confirmation link is good for one use within an hour of being sent.
