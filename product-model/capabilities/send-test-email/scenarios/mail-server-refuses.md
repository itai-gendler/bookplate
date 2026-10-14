---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader sends a test email
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::security } }
  - text: The mail server refuses it
    kind: condition
    entities: []
    contexts: { web: { place: web::signed-in::security } }
  - text: The Product shows exactly what the mail server said, unlike every other email
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::security } }
---

# Mail server refuses

## Trigger

The server's email settings are wrong.

## Outcome

The Reader sees the reason, to fix the settings.
