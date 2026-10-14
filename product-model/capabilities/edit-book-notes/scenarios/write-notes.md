---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Edit on a Book's page that has no notes yet
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Reader writes, with headings, emphasis, lists, quotes and callouts rendering as they type, and chooses Save
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Product keeps the notes as the Book's Notes page and returns the page to reading
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: notes-page, effect: creates, facts: [Text] }
    contexts: { web: { place: web::signed-in::book-page } }
---

# Write notes

## Trigger

The Reader has thoughts on a Book worth keeping.

## Outcome

The Book has a Notes page, and Saved shows beside it.

## Edge cases

- Save with nothing changed just puts the editor away.
- Leaving the page with unsaved changes asks first.
