---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader opens Statistics
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::statistics } }
  - text: "The Product shows the Books read, read this year and pages read, and the average rating of the rated Books read to the end"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Pages, Rating, Date finished] }
    contexts: { web: { place: web::signed-in::statistics } }
  - text: The Product lists the Books being read, furthest along first, with their percentage and days left, and how many days tracked Books took on average
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Date finished] }
      - { entity: progress-update, effect: reads, facts: [Day, Percentage] }
    contexts: { web: { place: web::signed-in::statistics } }
  - text: "The Product charts Books finished by year, ratings given, the six commonest genres and the rest as Other, and, where Source is switched on, where the Books came from"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Date finished, Rating, Genre, Source] }
      - { entity: reader, effect: reads, facts: [Optional features] }
    contexts: { web: { place: web::signed-in::statistics } }
---

# Read the statistics

## Trigger

The Reader wants to see their reading counted.

## Outcome

The Reader sees their totals, what is on the go and how the shelf divides.

## Edge cases

- A Book read without a date finished counts as read but in no year.
- Books with no genre or source count under Unspecified.
