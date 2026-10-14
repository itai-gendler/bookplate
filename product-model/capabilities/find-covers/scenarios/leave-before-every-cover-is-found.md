---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader chooses Stop while covers are being found
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product stops after the current Book and offers to find covers for the rest later
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Leave before every cover is found

## Trigger

The Reader needs to leave before every cover is found.

## Outcome

Covers found so far are kept, and the rest can be looked up with the same button.
