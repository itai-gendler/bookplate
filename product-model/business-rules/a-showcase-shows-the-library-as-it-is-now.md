---
appliesTo:
  - { type: capability, id: view-showcase }
  - { type: entity, id: showcase }
references:
  - { kind: code, role: implementation, target: lib/showcase.ts#loadShowcase }
---

# A showcase shows the library as it is when it is opened

A Showcase keeps only its Reader's choices; its Books, numbers and progress are read from the library each time it is opened, so it keeps up as the Reader reads.
