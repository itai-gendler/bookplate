---
kind: edge
routes:
  web: Web
steps:
  - text: "Where accounts must confirm their address, an account has gone seven days without confirming and has never signed in or stored anything"
    kind: condition
    unattended: true
    entities:
      - { entity: reader, effect: reads, facts: [Email confirmed] }
    contexts: { web: { place: web::public } }
  - text: The Product removes the account
    kind: product
    entities:
      - { entity: reader, effect: removes }
    contexts: { web: { place: web::public } }
---

# Unconfirmed account removed

## Trigger

The Product tidies up, at start and every six hours.

## Outcome

The address is free to sign up again.
