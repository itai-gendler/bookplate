---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader turns on Show notes
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::library } }
  - text: The Product drapes a bookmark ribbon over every Book that has a Notes page or a short note, in the covers and in the Ledger
    kind: product
    actor: reader
    entities:
      - { entity: notes-page, effect: reads, facts: [] }
      - { entity: book, effect: reads, facts: [Short note] }
    contexts: { web: { place: web::signed-in::library } }
---

# Mark the books with notes

## Trigger

The Reader wants to see which Books they have written about.

## Outcome

Every Book with notes carries a ribbon until Show notes is turned off.
