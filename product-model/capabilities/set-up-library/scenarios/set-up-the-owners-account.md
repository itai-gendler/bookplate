---
kind: primary
routes:
  web: Web
steps:
  - text: No account exists on the server yet
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Owner account] }
    contexts: { web: { place: web::public::set-up } }
  - text: The Visitor opens Bookplate and is brought to Set up your library
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::set-up } }
  - text: The Visitor enters their name, email and a password of at least eight characters and chooses Create account
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::set-up } }
  - text: The Product makes the owner's account, signs them in and opens their empty library
    kind: product
    actor: visitor
    entities:
      - { entity: reader, effect: creates, facts: [Name, Email, Password, Email confirmed] }
      - { entity: server-configuration, effect: changes, facts: [Owner account] }
    contexts: { web: { place: web::public::set-up } }
---

# Set up the owner's account

## Trigger

Someone opens a newly installed Bookplate for the first time.

## Outcome

The server has its owner, signed in to an empty library; with registration closed, nobody else can sign up.

## Edge cases

- A blank name is kept as Reader.
- Once the account exists, the set-up page leads to sign-in.
- Where registration is open and email is set up, the owner too confirms their address before signing in.
