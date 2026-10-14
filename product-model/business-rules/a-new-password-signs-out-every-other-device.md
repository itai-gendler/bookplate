---
appliesTo:
  - { type: capability, id: change-password }
  - { type: capability, id: reset-password }
  - { type: capability, id: reset-password-on-server }
  - { type: entity, id: reader, facts: [Password] }
references:
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: code, role: implementation, target: scripts/reset-password.mjs }
---

# A new password signs out every other device

Changing the password signs out every other device; resetting it, by email or on the server, signs out every device.
