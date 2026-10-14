---
appliesTo:
  - type: entity
    id: word
    effect: removes
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# Only its reader forgets a word

A Word is struck from a registry only by the Reader who kept it, on its own or with their account.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
