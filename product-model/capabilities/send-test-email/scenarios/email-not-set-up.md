---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader opens Security
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::security } }
  - text: The server cannot send email
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Email] }
    contexts: { web: { place: web::signed-in::security } }
  - text: "The Product says email isn't set up, so forgotten passwords are reset by whoever runs the server, and offers no test email"
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::security } }
---

# Email not set up

## Trigger

The Reader opens Security on a server without email.

## Outcome

The Reader knows how passwords are reset on this server.
