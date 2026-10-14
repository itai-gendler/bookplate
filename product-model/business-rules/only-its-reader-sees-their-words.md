---
appliesTo:
  - type: entity
    id: word
    effect: reads
permits:
  - related: [{ verb: owns, entity: reader }]
references:
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
---

# Only its reader sees their words

The vocabulary registry and the words on a Book's page are seen only by the Reader who kept them.

## Rationale

Every record belongs to one reader, and the server answers every request only with the signed-in reader's own records.
