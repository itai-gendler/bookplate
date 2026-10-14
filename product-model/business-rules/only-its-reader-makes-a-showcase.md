---
appliesTo:
  - type: entity
    id: showcase
    effect: creates
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/showcase.ts#saveShowcase }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# A reader makes showcases only of their own reading

A Showcase is made by a Reader, of their own library.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
