---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Finished Reading on the details of a Book they are reading
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product asks for the date finished, today unless the Book already has one, and the rating
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Date finished, Rating] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Reader picks the date and stars and chooses Mark as read
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product shelves the Book as Read with that date and rating
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, from: Reading, to: Read, facts: [Date finished, Rating] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Mark a book as read

## Trigger

The Reader reaches the end of a Book.

## Outcome

The Book is Read, counted in the year it was finished.

## Edge cases

- Cancel, or Escape, closes the question and leaves the Book as it was.
