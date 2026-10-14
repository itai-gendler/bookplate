---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader edits a Book and uploads, pastes or fetches from the catalogue a new cover image
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Reader crops the image to book proportions and chooses Save changes
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product stores the new cover in place of the old one
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, facts: [Cover photo] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Replace the cover

## Trigger

The Reader wants a Book to wear a different cover.

## Outcome

The Book shows the new cropped cover.

## Edge cases

- If the new cover cannot be stored, the Book is saved with its previous cover and the reason is shown.
