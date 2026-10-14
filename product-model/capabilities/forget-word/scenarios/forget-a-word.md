---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses to remove a Word from the registry
    kind: actor
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [Word] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product asks whether to forget the Word, naming it
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Reader chooses Forget it
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product removes the Word from the registry
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: removes }
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Forget a word

## Trigger

The Reader no longer wants a Word in their registry.

## Outcome

The Word is gone from the registry and from its Book's page.

## Edge cases

- Keep it closes the question and keeps the Word.
