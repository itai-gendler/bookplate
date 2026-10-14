---
kind: primary
routes:
  web: Web
steps:
  - text: The Visitor chooses Create an account on the sign-in page
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
  - text: The Visitor enters their name, email and a password of at least eight characters, ticks the newsletter box if they want it, and chooses Create account
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-up } }
  - text: The server cannot send email, so no confirmation is asked for
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Email] }
    contexts: { web: { place: web::public::sign-up } }
  - text: The Product makes the account, signs them in and opens their empty library
    kind: product
    actor: visitor
    entities:
      - { entity: reader, effect: creates, facts: [Name, Email, Password, Email confirmed, Newsletter] }
    contexts: { web: { place: web::public::sign-up } }
---

# Create an account

## Trigger

Someone wants a library on a server with open registration.

## Outcome

The new Reader is signed in to an empty library of their own.

## Edge cases

- The page has the browser solve an invisible puzzle while the Visitor types; it can be switched off on the server.
- The newsletter box is offered only where the server has a newsletter, and starts unticked.
- Where the server has a privacy policy or terms, the page says creating an account agrees to them.
- An address that already has an account gets the same answer, and that account is left as it was.
