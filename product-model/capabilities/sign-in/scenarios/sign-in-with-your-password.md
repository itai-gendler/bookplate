---
kind: primary
routes:
  web: Web
steps:
  - text: The Visitor enters their email and password and chooses Sign in
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
  - text: The Product checks them against the account, signs the Visitor in and opens their library
    kind: product
    actor: visitor
    entities:
      - { entity: reader, effect: reads, facts: [Email, Password, Email confirmed] }
    contexts: { web: { place: web::public::sign-in } }
---

# Sign in with your password

## Trigger

A reader comes back to their library.

## Outcome

The reader is signed in, for 30 days from their last visit on that device.

## Edge cases

- A wrong email or password is refused with a message.
- Every page of the library sends someone who is not signed in to sign in.
