---
appliesTo:
  - { type: capability, id: create-account }
  - { type: capability, id: sign-in }
  - { type: capability, id: confirm-email-address }
  - { type: entity, id: reader, facts: [Email confirmed] }
references:
  - { kind: code, role: implementation, target: lib/config.ts }
  - { kind: code, role: implementation, target: lib/auth.ts }
---

# Where registration is open and email is set up, an account signs in only once its address is confirmed

Such a server emails every new account a confirmation link; a server with registration closed, or without email, never asks.
