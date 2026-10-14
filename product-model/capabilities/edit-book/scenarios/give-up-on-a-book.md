---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Reader edits a Book they are reading, picks Didn't finish, sets the date they stopped and chooses Save changes"
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: "The Product saves the Book as Didn't finish, its date labelled Stopped"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, from: Reading, to: "Didn't finish", facts: [Date finished] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Give up on a book

## Trigger

The Reader stops reading a Book for good.

## Outcome

The Book is shelved as Didn't finish with the day the Reader stopped.

## Edge cases

- A Book the Reader didn't finish keeps its rating out of averages and the ratings chart.
