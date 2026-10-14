---
kind: primary
routes:
  web: Web
steps:
  - text: The Visitor follows the confirmation link in the email
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public } }
  - text: The Product confirms the address, signs the account in and opens its library
    kind: product
    actor: visitor
    entities:
      - { entity: reader, effect: changes, facts: [Email confirmed] }
    contexts: { web: { place: web::public::sign-in } }
---

# Confirm your address

## Trigger

A new account's owner opens the email Bookplate sent them.

## Outcome

The account is confirmed and in use.
