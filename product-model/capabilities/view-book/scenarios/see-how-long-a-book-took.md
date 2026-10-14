---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader picks a Book they have read
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The Book is Read and has Progress updates from before its date finished
    kind: condition
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Date finished] }
      - { entity: progress-update, effect: reads, facts: [Day] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product shows the Book's details with how many days it was read in, from the first Progress update to the date finished
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Rating, Date finished] }
      - { entity: progress-update, effect: reads, facts: [Day] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# See how long a book took

## Trigger

The Reader opens a Book whose reading they tracked to the end.

## Outcome

The Reader sees that the Book was read in a number of days, at least one.
