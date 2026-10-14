---
appliesTo:
  - type: entity
    id: book
    effect: removes
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# Only its reader deletes a book

A Book is deleted only by the Reader who owns it, on its own or with their account.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
