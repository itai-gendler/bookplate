---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader picks a year's column in Books finished by year
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::statistics } }
  - text: The Product lists that year's finished Books in the order they were finished, with the year's books, pages and average rating, and its highest-rated Books first when they are not all rated alike
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Pages, Rating, Date finished, Binding colour] }
    contexts: { web: { place: web::signed-in::statistics } }
---

# Drill into a year

## Trigger

The Reader wonders what they read in a given year.

## Outcome

The Reader sees that year's Books, any of which opens its details.
