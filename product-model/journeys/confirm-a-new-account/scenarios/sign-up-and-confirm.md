---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: The Visitor enters their name, email and password on Create an account and chooses Create account
    kind: actor
    actor: visitor
    capability: create-account
    entities: []
    contexts: { web: { place: web::public::sign-up } }
  - text: The Product makes the account unconfirmed, emails a confirmation link and asks the Visitor to check their inbox
    kind: product
    actor: visitor
    capability: create-account
    entities:
      - { entity: reader, effect: creates, facts: [Name, Email, Password, Email confirmed, Newsletter] }
    contexts: { web: { place: web::public::sign-up } }
  - text: The Visitor opens the email and follows the link
    kind: actor
    actor: visitor
    capability: confirm-email-address
    entities: []
    contexts: { web: { place: web::public } }
  - text: The Product confirms the address, signs the account in and opens its library
    kind: product
    actor: visitor
    capability: confirm-email-address
    entities:
      - { entity: reader, effect: changes, facts: [Email confirmed] }
    contexts: { web: { place: web::public::sign-in } }
---

# Sign up and confirm

## Trigger

Someone signs up on a server with open registration and email.

## Outcome

Their account is confirmed and they are in their library.

## Edge cases

- Signing in before confirming sends a fresh link instead.
