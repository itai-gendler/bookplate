---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader switches the Library to the Ledger
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::library } }
  - text: "The Product lists each Book with its title, author, genre, rating and date finished, and whether a physical copy is owned where Copy is switched on"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Genre, Rating, Date finished, Physical copy, Binding colour] }
      - { entity: reader, effect: reads, facts: [Optional features] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The Product ends the Ledger with a count of the volumes shown and how many are read, reading, TBR and didn't finish
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::library } }
---

# Read the ledger

## Trigger

The Reader wants the shelf as a table rather than covers.

## Outcome

The Reader sees every matching Book as a row, with the totals of what is shown.

## Edge cases

- The count row follows the active search and status filter.
