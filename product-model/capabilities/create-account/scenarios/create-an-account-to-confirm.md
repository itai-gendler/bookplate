---
kind: alternative
routes:
  web: Web
steps:
  - text: The Visitor enters their name, email and password on Create an account and chooses Create account
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-up } }
  - text: The server can send email, so new accounts must confirm their address
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Email] }
    contexts: { web: { place: web::public::sign-up } }
  - text: The Product makes the account unconfirmed and emails a confirmation link that works for an hour
    kind: product
    actor: visitor
    entities:
      - { entity: reader, effect: creates, facts: [Name, Email, Password, Email confirmed, Newsletter] }
    contexts: { web: { place: web::public::sign-up } }
  - text: The Product asks the Visitor to check their inbox
    kind: product
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-up } }
---

# Create an account to confirm

## Trigger

Someone signs up on a server with open registration and email.

## Outcome

The account exists, waiting for its address to be confirmed before it can sign in.
