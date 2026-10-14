---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader opens the page of a Book that has been deleted
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-page } }
  - text: No such Book is in the library
    kind: condition
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Product says the book is no longer on the shelf and offers the way back to the library
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-page } }
---

# Book no longer on the shelf

## Trigger

The Reader follows an old link to a Book's page.

## Outcome

The Reader is told the Book is gone.
