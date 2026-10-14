---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Notes on a Book's details
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: "The Product opens the Book's page: its cover, status, title, author, rating, genre and pages, then its notes rendered with their pasted images"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Rating, Genre, Pages, Cover photo] }
      - { entity: notes-page, effect: reads, facts: [Text, Pasted images] }
    contexts: { web: { place: web::signed-in::book-page } }
---

# Read a book's notes

## Trigger

The Reader wants to revisit what they wrote about a Book.

## Outcome

The Reader reads the Book's notes on its own page.

## Edge cases

- A Book with no notes yet says nothing is written and to press Edit to start.
- A Book with a short note from before notes pages opens with that note, which becomes its Notes page once saved.
- The Book's page counts as the Library in the sections bar.
