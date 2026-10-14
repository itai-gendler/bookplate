---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader imports a later export from the same service
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product matches each row to a Book already here, by the id an earlier import gave it, then ISBN, then title and author
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, ISBN] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product updates the reading details of each matched Book in place, keeping its cover, colour, genre, source and notes
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, facts: [ISBN, Pages, Rating, Date finished, Physical copy] }
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Reimport an export

## Trigger

The Reader imports a newer export from the same service.

## Outcome

The Books already here are brought up to date, with nothing duplicated.

## Edge cases

- A review becomes a notes page only for a Book that has none yet.
- A rating left empty in the export keeps the Book's rating.
