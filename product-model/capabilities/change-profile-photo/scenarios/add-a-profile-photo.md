---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Add a photo, or Change photo, and picks an image
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::profile } }
  - text: The Reader positions and zooms it inside a circle and chooses Use this photo
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::profile } }
  - text: The Product stores the cropped photo, replaces any earlier one and shows it in the account menu
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: changes, facts: [Profile photo] }
    contexts: { web: { place: web::signed-in::profile } }
---

# Add a profile photo

## Trigger

The Reader wants their own picture on their account.

## Outcome

The Reader's photo shows in Settings and the account menu.

## Edge cases

- A photo beyond the account's image space is refused with a message.
