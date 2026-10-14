---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader switches off Source or Copy
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::preferences } }
  - text: The Product saves the choice and hides the detail everywhere, keeping every value already recorded
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: changes, facts: [Optional features] }
    contexts: { web: { place: web::signed-in::preferences } }
---

# Switch off an optional detail

## Trigger

The Reader no longer wants to see a detail.

## Outcome

The detail is hidden, and comes back with its values when switched on again.
