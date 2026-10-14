---
appliesTo:
  - type: entity
    id: book
    effect: creates
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# A reader adds books only to their own library

Adding a Book, by hand, from the catalogue or by import, puts it in the adding Reader's own library.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
