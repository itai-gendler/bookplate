---
appliesTo:
  - { type: capability, id: delete-book }
  - { type: capability, id: delete-account }
references:
  - { kind: code, role: implementation, target: lib/library.ts#deleteBook }
---

# A deleted book takes its notes, pasted images, cover and progress with it

Nothing a Book kept outlives it. The Words learned from it stay in the registry, no longer tied to a Book on the shelf.
