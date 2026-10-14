---
kind: primary
routes:
  web: Web
steps:
  - text: The Visitor follows Privacy policy from the sign-in or sign-up page
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-in } }
  - text: The Product shows the policy the server's operator wrote, with when it was last changed
    kind: product
    actor: visitor
    entities:
      - { entity: server-configuration, effect: reads, facts: [Privacy policy] }
    contexts: { web: { place: web::public::privacy-policy } }
---

# Read the privacy policy

## Trigger

Someone wants to know how this server treats their data.

## Outcome

The Visitor reads the policy.

## Edge cases

- Where the policy is published on another site, the link and the policy's address lead there.
- A server with no policy shows no link.
