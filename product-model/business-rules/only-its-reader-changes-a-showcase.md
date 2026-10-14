---
appliesTo:
  - type: entity
    id: showcase
    effect: changes
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/showcase.ts#saveShowcase }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# Only its reader changes a showcase

What a Showcase shows and the name on it are changed only by the Reader whose it is.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
