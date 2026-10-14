---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader edits a Book with a cover photo, chooses Remove image and then Save changes
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product deletes the stored cover, and the Book wears its generated cloth cover again
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, facts: [Cover photo] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Remove the cover

## Trigger

The Reader prefers the generated cover to the photo.

## Outcome

The Book wears its cloth cover in its binding colour.
