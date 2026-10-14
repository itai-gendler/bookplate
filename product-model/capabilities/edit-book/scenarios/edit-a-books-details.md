---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses to edit the Book from its details
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product opens the form filled with the Book's details
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Genre, Pages, Source, Physical copy, Rating, Date finished, Cover photo] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Reader changes the title, author, genre, pages, rating, date finished, and source and copy where switched on, and chooses Save changes
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product saves the Book
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, facts: [Title, Author, Genre, Pages, Source, Physical copy, Rating, Date finished] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Edit a book's details

## Trigger

Something about a Book on the shelf is wrong or has changed.

## Outcome

The Book shows its new details everywhere in the library.

## Edge cases

- Details hidden in Preferences are saved back unchanged.
- A source typed to match a built-in one, such as "kindle", becomes that built-in source.
