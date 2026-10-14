---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader pastes or drops an image into the notes while editing
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Product shrinks a large image to a 1600-pixel long edge as JPEG, stores it and shows it inline where it was placed
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Reader goes on writing, perhaps deleting an earlier image, and chooses Save
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Product saves the whole note and deletes every stored image the text no longer uses
    kind: product
    actor: reader
    entities:
      - { entity: notes-page, effect: changes, facts: [Text, Pasted images] }
    contexts: { web: { place: web::signed-in::book-page } }
---

# Paste an image into notes

## Trigger

The Reader wants a photo or screenshot in their notes.

## Outcome

The image is part of the notes, and no image the notes stopped using is kept.

## Edge cases

- GIFs and small images are stored as they are.
- An image of a kind Bookplate does not store, or beyond the server's limits, is refused with a message and the notes are unchanged.
