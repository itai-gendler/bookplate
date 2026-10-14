---
kind: primary
routes:
  web: Web
steps:
  - text: The server can send email
    kind: condition
    entities:
      - { entity: server-configuration, effect: reads, facts: [Email] }
    contexts: { web: { place: web::signed-in::security } }
  - text: The Reader chooses Send a test email to their address
    kind: actor
    actor: reader
    entities:
      - { entity: reader, effect: reads, facts: [Email] }
    contexts: { web: { place: web::signed-in::security } }
  - text: The Product sends the test email and says where it went
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: reads, facts: [Email] }
    contexts: { web: { place: web::signed-in::security } }
---

# Send a test email

## Trigger

The Reader, often the server's owner, wants to know email is working.

## Outcome

A test email is on its way to the Reader's inbox.

## Edge cases

- A few test emails in a short time are allowed, then the Reader is asked to wait.
- The emails count towards the server's daily email cap.
