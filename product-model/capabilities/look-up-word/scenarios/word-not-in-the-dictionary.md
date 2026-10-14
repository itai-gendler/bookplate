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
  - text: Wiktionary has no English entry for it
    kind: condition
    entities: []
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product says the dictionary has no entry and opens a form to record the word in the Reader's own words
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Word not in the dictionary

## Trigger

The Reader looks up a word Wiktionary doesn't know.

## Outcome

The Reader is offered to define it themselves.
