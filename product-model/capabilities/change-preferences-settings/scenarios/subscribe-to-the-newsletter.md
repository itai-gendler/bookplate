---
kind: alternative
routes:
  web: Web
steps:
  - text: The server offers a newsletter
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Newsletter offered] }
    contexts: { web: { place: web::signed-in::preferences } }
  - text: The Reader switches on the newsletter
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::preferences } }
  - text: "The Product records that the Reader asked for it, keeping the time they first agreed, and says they're subscribed"
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: changes, facts: [Newsletter] }
    contexts: { web: { place: web::signed-in::preferences } }
---

# Subscribe to the newsletter

## Trigger

The Reader wants the occasional newsletter from whoever runs the server.

## Outcome

The Reader is recorded as subscribed; sending it is up to the server operator.

## Edge cases

- Switching it off records that the Reader is unsubscribed.
- Without a newsletter on the server the switch is not offered.
