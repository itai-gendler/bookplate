---
appliesTo:
  - type: entity
    id: showcase
    effect: removes
permits:
  - related: [{ verb: owns, entity: reader }]
  - actors: [server-operator]
references:
  - { kind: code, role: implementation, target: lib/showcase.ts#deleteShowcase }
  - { kind: code, role: implementation, target: scripts/remove-showcase.mjs }
---

# A showcase is turned off by its reader or taken down by the server operator

A Showcase is deleted by the Reader whose it is, or, when it is reported, by whoever runs the server; nobody else can stop it.
