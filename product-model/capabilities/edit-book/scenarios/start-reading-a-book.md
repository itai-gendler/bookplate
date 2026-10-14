---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader edits a TBR Book, picks Reading and chooses Save changes
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product saves the Book as Reading
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, from: TBR, to: Reading, facts: [] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Start reading a book

## Trigger

The Reader begins a Book that was waiting on the shelf.

## Outcome

The Book is Reading, and its details offer progress logging.
