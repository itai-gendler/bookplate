---
appliesTo:
  - type: entity
    id: progress-update
    effect: removes
permits:
  - related: [{ verb: has, entity: book }, { verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# Only its reader removes a progress update

A Progress update is removed only by the Reader who owns the Book.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
