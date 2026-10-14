---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader keeps the page open while covers are being found
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The next cover would take the account past its image space
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Image space limit] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product stops finding covers and says there is no room for more
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Image space runs out

## Trigger

The account's images reach the server's limit while covers are being found.

## Outcome

The covers found so far are kept and the Reader knows why it stopped.
