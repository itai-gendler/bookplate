---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Remove photo
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::profile } }
  - text: The Product deletes the photo, and the default bookshelf picture shows instead
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: changes, facts: [Profile photo] }
    contexts: { web: { place: web::signed-in::profile } }
---

# Remove the profile photo

## Trigger

The Reader no longer wants a photo on their account.

## Outcome

The account shows the default picture.
