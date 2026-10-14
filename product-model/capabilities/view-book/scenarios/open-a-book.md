---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader picks a Book on the shelf
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title] }
    contexts: { web: { place: web::signed-in::library } }
  - text: "The Product opens the Book's details: its status, title, author, rating or Not yet rated, genre, pages, date finished, labelled Stopped for a Book the Reader didn't finish, and whether it has notes"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Rating, Genre, Pages, Date finished, Cover photo, Binding colour, Short note] }
      - { entity: notes-page, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product adds the Book's source and whether a physical copy is owned where the Reader has switched those details on
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: reads, facts: [Optional features] }
      - { entity: book, effect: reads, facts: [Source, Physical copy] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Open a book

## Trigger

The Reader wants to look at one Book.

## Outcome

The Reader sees the Book's details, with the ways to finish it, open its notes, edit it or delete it.

## Edge cases

- A Book being read also shows its progress, covered by Log reading progress.
