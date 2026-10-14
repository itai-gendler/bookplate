---
kind: edge
routes:
  web: Web
steps:
  - text: The Visitor follows a reset link that is over an hour old or already used
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::choose-a-new-password } }
  - text: The Product says the link has expired or was used, that reset links work once for an hour, and offers to send a new one
    kind: product
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::choose-a-new-password } }
---

# Reset link expired

## Trigger

A reader opens an old reset email.

## Outcome

The password is unchanged; a new link is one step away.
