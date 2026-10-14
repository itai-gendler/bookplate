---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader edits a Book's notes, perhaps pasting images, and chooses Cancel
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Product puts the saved notes back, deletes the images pasted since the last save that they do not use, and returns the page to reading
    kind: product
    actor: reader
    entities:
      - { entity: notes-page, effect: reads, facts: [Text] }
    contexts: { web: { place: web::signed-in::book-page } }
---

# Discard note edits

## Trigger

The Reader changes their mind about an edit.

## Outcome

The notes are exactly as last saved.
