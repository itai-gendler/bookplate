---
appliesTo:
  - type: entity
    id: word
    effect: creates
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# A reader keeps words only in their own registry

A Word kept or imported goes into the keeping Reader's own registry.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
