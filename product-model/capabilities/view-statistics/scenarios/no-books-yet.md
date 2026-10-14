---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader opens Statistics
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::statistics } }
  - text: The library has no Books
    kind: condition
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::statistics } }
  - text: The Product says there is nothing to count yet and to add a book from the library
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::statistics } }
---

# No books yet

## Trigger

A new Reader opens Statistics.

## Outcome

The Reader is pointed to the Library.
