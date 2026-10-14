---
kind: validation
routes:
  web: Web
steps:
  - text: The Visitor signs in to an account after too many wrong passwords for it
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
  - text: The Product refuses and says how many minutes to wait
    kind: product
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
---

# Too many wrong passwords

## Trigger

Someone keeps getting an account's password wrong.

## Outcome

Signing in to that account pauses for a while; a password reset lifts the pause.
