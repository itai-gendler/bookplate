---
appliesTo:
  - type: entity
    id: showcase
    effect: reads
permits:
  - related: [{ verb: owns, entity: reader }]
  - actors: [visitor]
  - actors: [server-operator]
references:
  - { kind: code, role: implementation, target: lib/showcase.ts#loadShowcase }
  - { kind: code, role: implementation, target: "app/s/[id]/page.tsx" }
  - { kind: code, role: implementation, target: proxy.ts }
---

# Anyone with its link opens a showcase

A Showcase is public to whoever has its link, signed in or not; its Reader also sees it, with its link, in Settings, and whoever runs the server reaches it by the link it was reported with.

## Rationale

The link is long and random, and the page asks search engines not to list it, so only people the Reader sends it to find it.
