---
appliesTo:
  - type: entity
    id: reader
    effect: changes
    facts: [Password]
permits:
  - self: true
  - actors: [visitor]
  - actors: [server-operator]
references:
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: code, role: implementation, target: scripts/reset-password.mjs }
---

# A password is changed by its reader, through an emailed reset link, or on the server

A Reader changes their own password knowing the current one. Signed out, it
changes only through a reset link emailed to the account's address, or by
whoever runs the server with the reset-password command.
