---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader looks up a word
    kind: actor
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: Wiktionary cannot be reached or fails
    kind: condition
    entities: []
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product says the dictionary could not be reached and to try again in a moment
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Dictionary unreachable

## Trigger

The Reader looks a word up while Wiktionary is unavailable.

## Outcome

Nothing is shown or kept; the Reader can try again.
