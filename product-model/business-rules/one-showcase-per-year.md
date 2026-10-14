---
appliesTo:
  - { type: capability, id: make-showcase }
  - { type: capability, id: edit-showcase }
  - { type: entity, id: showcase }
references:
  - { kind: code, role: implementation, target: lib/showcase.ts#saveShowcase }
  - { kind: code, role: implementation, target: lib/db/schema.ts }
---

# A reader has at most one showcase for each year, and changing it keeps its link

Saving a year that already has a Showcase changes that Showcase; its link stays the one already sent.
