---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader picks a Book in a statistics drill-down or under Currently reading
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title] }
    contexts: { web: { place: web::signed-in::statistics } }
  - text: The Product opens the Library with that Book's details open
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Rating, Genre, Pages, Date finished, Cover photo] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Open a book from statistics

## Trigger

Something the Reader sees on the Statistics page makes them want to look at a Book.

## Outcome

The Reader is at the Book's details in the Library, where editing and notes live.
