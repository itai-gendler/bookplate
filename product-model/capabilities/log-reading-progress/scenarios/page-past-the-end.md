---
kind: validation
routes:
  web: Web
steps:
  - text: The Reader enters a page beyond the Book's page count, or a percentage outside 0 to 100
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Pages] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product records nothing and asks for a page from 0 to the page count, or a percentage from 0 to 100
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-details } }
---

# Page past the end

## Trigger

The Reader mistypes their progress.

## Outcome

No update is recorded and the Reader is told the range.
