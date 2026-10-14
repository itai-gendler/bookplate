---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Reader chooses Finished Reading on a Book they didn't finish"
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Reader keeps or changes the date and rating and chooses Mark as read
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Date finished, Rating] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product shelves the Book as Read
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, from: "Didn't finish", to: Read, facts: [Date finished, Rating] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Finish a book you gave up

## Trigger

The Reader went back to a Book they had stopped and read it to the end.

## Outcome

The Book is Read; its rating now counts.

## Edge cases

- Finished Reading is offered on every Book that is not already Read, TBR included.
