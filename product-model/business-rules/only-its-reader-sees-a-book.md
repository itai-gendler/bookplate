---
appliesTo:
  - type: entity
    id: book
    effect: reads
    contexts: [{ place: web::signed-in }]
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# Only its reader sees a book in their library

A Book is seen in the library, its details, its page, Vocabulary and Statistics only by the Reader who owns it.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
