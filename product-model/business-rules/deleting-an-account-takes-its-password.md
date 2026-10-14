---
appliesTo:
  - { type: capability, id: delete-account }
  - { type: entity, id: reader }
references:
  - { kind: code, role: implementation, target: app/api/account/route.ts }
---

# Deleting an account always takes its password

However recently the Reader signed in, deleting the account asks for the password, and a wrong one deletes nothing.

## Rationale

A device left signed in is not enough to wipe a library.
