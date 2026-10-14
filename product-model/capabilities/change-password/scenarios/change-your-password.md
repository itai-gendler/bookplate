---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader enters their current password and a new one of at least eight characters twice, and chooses Change password
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::security } }
  - text: The Product changes the password and signs out every other device
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: changes, facts: [Password] }
    contexts: { web: { place: web::signed-in::security } }
---

# Change your password

## Trigger

The Reader wants a new password.

## Outcome

The new password works, and anyone signed in elsewhere is signed out.
