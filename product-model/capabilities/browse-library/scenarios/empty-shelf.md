---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader opens the Library or narrows it
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::library } }
  - text: No Book is in the library or matches the status and search
    kind: condition
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The Product says the shelf is empty and suggests adding one or clearing the filter
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::library } }
---

# Empty shelf

## Trigger

The Reader's library is empty, or nothing matches what they narrowed it to.

## Outcome

The Reader is told the shelf is empty and how to fill it.
