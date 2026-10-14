---
kind: edge
routes:
  web: Web
steps:
  - text: The Reader chooses Save while the server cannot be reached
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Product says the notes could not be saved and keeps the editor open with the Reader's text
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-page } }
---

# Notes not saved

## Trigger

Saving notes fails.

## Outcome

Nothing is lost from the editor; the Reader can save again.
