---
kind: validation
routes:
  web: Web
steps:
  - text: The Reader enters a password that is not theirs and chooses Delete my account and library
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::delete-account } }
  - text: "The Product deletes nothing and says the password isn't right"
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::delete-account } }
---

# Wrong password keeps the account

## Trigger

The Reader mistypes their password, or someone else is at their device.

## Outcome

The account is untouched.

## Edge cases

- After too many wrong passwords, deleting pauses for some minutes.
