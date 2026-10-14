---
kind: validation
routes:
  web: Web
steps:
  - text: The Reader keeps a word
    kind: actor
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The registry already holds as many words as the server's word limit
    kind: condition
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
      - { entity: server-configuration, effect: reads, facts: [Word limit] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product keeps nothing, takes the word back off the list and says the registry has reached the server's limit
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Registry at its word limit

## Trigger

The Reader keeps a word in a registry that is full on this server.

## Outcome

The registry is unchanged and the Reader knows why.
