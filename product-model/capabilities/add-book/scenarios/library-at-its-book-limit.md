---
kind: validation
routes:
  web: Web
steps:
  - text: The Reader fills in a book and chooses Add to shelf
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The library already holds as many books as the server's book limit
    kind: condition
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: server-configuration, effect: reads, facts: [Book limit] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The Product keeps nothing, takes the book back off the shelf and says the library has reached the server's limit
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::library } }
---

# Library at its book limit

## Trigger

The Reader adds a book to a library that is full on this server.

## Outcome

The library is unchanged and the Reader knows why.
