---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader has not turned off the explanation of the vocabulary registry
    kind: condition
    entities:
      - { entity: reader, effect: reads, facts: [Dismissed hints] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product shows what the vocabulary registry is for at the top of Vocabulary
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: "The Reader chooses Don't show again"
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product hides it and keeps the choice on the Reader's account
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: changes, facts: [Dismissed hints] }
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Turn off the vocabulary hint

## Trigger

The Reader knows what the registry is for.

## Outcome

The explanation no longer shows on any device the Reader signs in on.
