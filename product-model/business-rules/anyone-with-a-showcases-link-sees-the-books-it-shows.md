---
appliesTo:
  - type: entity
    id: book
    effect: reads
    contexts: [{ place: web::public::showcase }]
  - type: entity
    id: progress-update
    effect: reads
    contexts: [{ place: web::public::showcase }]
permits:
  - actors: [visitor]
references:
  - { kind: code, role: implementation, target: "app/s/[id]/covers/[name]/route.ts" }
  - { kind: code, role: implementation, target: lib/showcase.ts#coverFileOf }
---

# Anyone with a showcase's link sees the books it shows

On a Showcase, anyone with the link sees the year's Books and how far along the Books being read are, with their covers.
