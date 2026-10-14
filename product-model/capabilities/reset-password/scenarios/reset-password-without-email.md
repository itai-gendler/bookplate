---
kind: alternative
routes:
  web: Web
steps:
  - text: The Visitor chooses Forgot password on the sign-in page
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
  - text: The server cannot send email
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Email] }
    contexts: { web: { place: web::public::forgot-password } }
  - text: The Product explains that whoever runs the server resets passwords with the reset-password command, which signs out every device
    kind: product
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::forgot-password } }
---

# Reset password without email

## Trigger

A reader forgets their password on a server that can't send email.

## Outcome

The reader knows to ask whoever runs the server.
