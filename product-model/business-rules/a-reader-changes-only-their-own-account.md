---
appliesTo:
  - type: entity
    id: reader
    effect: changes
    facts: [Name, Profile photo, Optional features, Newsletter, Dismissed hints]
permits:
  - self: true
references:
  - { kind: code, role: implementation, target: app/api/avatar/route.ts }
  - { kind: code, role: implementation, target: app/api/account/features/route.ts }
  - { kind: code, role: implementation, target: app/api/account/route.ts }
---

# A reader changes only their own photo and preferences

A Reader's profile photo, optional details, newsletter choice and dismissed hints are changed only by that Reader.
