---
kind: validation
routes:
  web: Web
steps:
  - text: The Reader imports a zip
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The new Books, Words or images would take the library past the server's book, word or image space limit
    kind: condition
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
      - { entity: book, effect: reads, facts: [] }
      - { entity: server-configuration, effect: reads, facts: [Book limit, Word limit, Image space limit] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product imports nothing and says which limit it would pass
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Import over the limits

## Trigger

The Reader imports more than this server allows one library.

## Outcome

Nothing of the zip is kept.
