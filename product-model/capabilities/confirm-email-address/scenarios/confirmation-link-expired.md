---
kind: edge
routes:
  web: Web
steps:
  - text: The Visitor follows a confirmation link that is over an hour old or already used
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public } }
  - text: The Product opens Sign in, saying the link has expired or was used and that signing in sends a new one
    kind: product
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
---

# Confirmation link expired

## Trigger

The account's owner opens an old confirmation email.

## Outcome

The address stays unconfirmed until a fresh link is followed.
