---
kind: validation
routes:
  web: Web
steps:
  - text: The Reader enters two different new passwords and chooses Change password
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::security } }
  - text: "The Product changes nothing and says the new passwords don't match"
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::security } }
---

# New passwords don't match

## Trigger

The Reader mistypes the new password.

## Outcome

The password is unchanged.

## Edge cases

- A wrong current password is refused the same way, with its own message.
