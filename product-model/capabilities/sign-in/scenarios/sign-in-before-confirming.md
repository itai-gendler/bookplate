---
kind: validation
routes:
  web: Web
steps:
  - text: The Visitor signs in to an account whose address must still be confirmed
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
  - text: The account has not confirmed its address
    kind: condition
    entities:
      - { entity: reader, effect: reads, facts: [Email confirmed] }
    contexts: { web: { place: web::public::sign-in } }
  - text: The Product refuses, emails a fresh confirmation link and says to confirm the address first
    kind: product
    actor: visitor
    entities:
      - { entity: reader, effect: reads, facts: [Email] }
    contexts: { web: { place: web::public::sign-in } }
---

# Sign in before confirming

## Trigger

A new account's owner tries to sign in without having confirmed.

## Outcome

The Visitor is not signed in and has a new link in their inbox.
