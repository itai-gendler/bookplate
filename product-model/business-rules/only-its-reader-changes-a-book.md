---
appliesTo:
  - type: entity
    id: book
    effect: changes
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# Only its reader changes a book

Editing a Book, finishing it or finding its cover is open only to the Reader who owns it.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
