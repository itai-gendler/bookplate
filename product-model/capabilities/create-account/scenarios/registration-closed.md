---
kind: validation
routes:
  web: Web
steps:
  - text: The Visitor goes to Create an account
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-up } }
  - text: Registration on this server is closed
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Registration] }
    contexts: { web: { place: web::public::sign-up } }
  - text: The Product sends the Visitor to sign in, offering no way to sign up
    kind: product
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
---

# Registration closed

## Trigger

Someone tries to sign up on a single-owner server.

## Outcome

No account is made.
