---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader searches the catalogue while adding a book
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: Open Library cannot be reached or fails
    kind: condition
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product says the catalogue could not be reached and that the details can still be filled in by hand
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
---

# Catalogue unreachable

## Trigger

The Reader searches the catalogue while it is unavailable.

## Outcome

The Reader can still add the book by hand.

## Edge cases

- A search that finds nothing says so and suggests a different title or the details by hand.
