---
kind: primary
routes:
  web: Web
steps:
  - text: The Visitor chooses Forgot password on the sign-in page
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
  - text: The server can send email
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Email] }
    contexts: { web: { place: web::public::forgot-password } }
  - text: The Visitor enters the email they sign in with and chooses Send reset link
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::forgot-password } }
  - text: The Product emails a link that works once, for an hour, to the address if it has an account, with the same message whether or not it has one
    kind: product
    actor: visitor
    entities:
      - { entity: reader, effect: reads, facts: [Email] }
    contexts: { web: { place: web::public::forgot-password } }
  - text: The Visitor follows the link, enters a new password twice and chooses Set new password
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::choose-a-new-password } }
  - text: The Product changes the password, counts the address as confirmed, lifts any wrong-password pause and signs out every device
    kind: product
    actor: visitor
    entities:
      - { entity: reader, effect: changes, facts: [Password, Email confirmed] }
    contexts: { web: { place: web::public::choose-a-new-password } }
---

# Reset a forgotten password

## Trigger

A reader can't remember their password.

## Outcome

The reader can sign in with the new password on every device.

## Edge cases

- At most three reset emails go to one address in fifteen minutes; beyond that nothing is sent and nothing is said.
- A failure to send is never shown to the Visitor.
