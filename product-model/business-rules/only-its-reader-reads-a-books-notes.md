---
appliesTo:
  - type: entity
    id: notes-page
    effect: reads
permits:
  - related: [{ verb: has, entity: book }, { verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
  - { kind: code, role: implementation, target: "app/api/notes/images/[book]/[name]/route.ts" }
---

# Only its reader reads a book's notes

A Notes page and its pasted images are read only by the Reader who owns its Book.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
