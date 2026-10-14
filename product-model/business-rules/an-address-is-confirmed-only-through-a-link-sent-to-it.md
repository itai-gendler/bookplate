---
appliesTo:
  - type: entity
    id: reader
    effect: changes
    facts: [Email confirmed]
permits:
  - actors: [visitor]
references:
  - { kind: code, role: implementation, target: lib/auth.ts }
---

# An address is confirmed only through a link emailed to it

An account's address counts as confirmed once someone follows a confirmation
or password reset link sent to it; nothing else confirms it.

## Rationale

Following such a link shows access to the inbox, so a reset also confirms an
account made before confirmation was required.
