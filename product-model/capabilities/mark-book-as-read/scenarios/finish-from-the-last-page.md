---
kind: alternative
routes:
  web: Web
steps:
  - text: The Book's latest Progress update is at the last page or 100 percent
    kind: condition
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: progress-update, effect: reads, facts: [Percentage] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: "The Product says that's the last page and offers Mark as finished"
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Reader chooses Mark as finished, then Mark as read with the date and rating
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product shelves the Book as Read
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, from: Reading, to: Read, facts: [Date finished, Rating] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Finish from the last page

## Trigger

The Reader logs the last page of a Book.

## Outcome

The Book is Read without the Reader looking for the Finished Reading button.
