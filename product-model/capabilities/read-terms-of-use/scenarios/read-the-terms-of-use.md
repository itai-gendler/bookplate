---
kind: primary
routes:
  web: Web
steps:
  - text: The Visitor follows Terms of use from the sign-in or sign-up page
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
  - text: The Product shows the terms the server's operator wrote, with when they were last changed
    kind: product
    actor: visitor
    entities:
      - { entity: server-configuration, effect: reads, facts: [Terms of use] }
    contexts: { web: { place: web::public::terms-of-use } }
---

# Read the terms of use

## Trigger

Someone wants to know the terms of this server before signing up.

## Outcome

The Visitor reads the terms.

## Edge cases

- Where the terms are published on another site, the link and the terms' address lead there.
