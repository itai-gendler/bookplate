---
kind: edge
routes:
  web: Web
steps:
  - text: The Visitor opens the link of a Showcase that has been turned off or taken down
    kind: actor
    actor: visitor
    entities:
      - { entity: showcase, effect: reads, facts: [] }
    contexts: { web: { place: web::public::showcase } }
  - text: No Showcase has that link
    kind: condition
    actor: visitor
    entities:
      - { entity: showcase, effect: reads, facts: [] }
    contexts: { web: { place: web::public::showcase } }
  - text: The Product answers that the page is not found
    kind: product
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::showcase } }
---

# Showcase turned off

## Trigger

The Visitor follows a link that no longer leads anywhere.

## Outcome

Nothing of the reader's library is shown.
