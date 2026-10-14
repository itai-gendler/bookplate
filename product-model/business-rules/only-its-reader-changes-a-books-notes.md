---
appliesTo:
  - type: entity
    id: notes-page
    effect: changes
permits:
  - related: [{ verb: has, entity: book }, { verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# Only its reader changes a book's notes

A Notes page is changed only by the Reader who owns its Book.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
