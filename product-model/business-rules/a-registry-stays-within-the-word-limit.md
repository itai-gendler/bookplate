---
appliesTo:
  - { type: capability, id: keep-word }
  - { type: capability, id: import-library }
  - { type: entity, id: server-configuration, facts: [Word limit] }
references:
  - { kind: code, role: implementation, target: lib/limits.ts#checkWords }
---

# A vocabulary registry never holds more words than the server's word limit

Where the server sets a word limit, keeping or importing past it is refused with the limit named.
