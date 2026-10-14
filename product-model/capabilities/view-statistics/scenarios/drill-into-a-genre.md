---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader picks a genre, or See all genres and then one of them
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::statistics } }
  - text: The Product lists that genre's Books, highest rated first
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Genre, Rating, Date finished] }
    contexts: { web: { place: web::signed-in::statistics } }
---

# Drill into a genre

## Trigger

The Reader wants the Books behind one bar of the genres chart.

## Outcome

The Reader sees that genre's Books.

## Edge cases

- A rating row lists the Books read with that rating, by title; a source row lists that source's Books, best first.
