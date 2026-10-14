---
appliesTo:
  - { type: capability, id: make-showcase }
  - { type: capability, id: edit-showcase }
  - { type: entity, id: showcase }
references:
  - { kind: code, role: implementation, target: lib/showcase.ts#parseShowcase }
  - { kind: code, role: implementation, target: lib/showcaseYear.ts#includesReading }
---

# Only this year's showcase shows what is being read

A Showcase of a past year shows the Books read only; books being read belong to the current year alone.
