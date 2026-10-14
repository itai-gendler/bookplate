---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Add book
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The Reader searches the Open Library catalogue for the book
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product asks Open Library and lists up to eight matches, each with its cover, author, year and page count
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Reader picks a match
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product fills in the title, author and page count, fetches the match's cover from Open Library or else from iTunes, and opens it to crop
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Reader crops the cover to book proportions and sets the genre, rating and date finished
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Reader chooses Add to shelf
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product stores the cover, compressed, and adds the Book as Read with a random binding colour
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: creates, to: Read, facts: [Title, Author, Pages, Genre, Rating, Date finished, Cover photo, Binding colour, Open Library work, Added] }
    contexts: { web: { place: web::signed-in::library } }
---

# Add a book from the catalogue

## Trigger

The Reader has a book to record and wants its details and cover found for them.

## Outcome

The Book is on the shelf with the catalogue's details and its cropped cover.

## Edge cases

- A new Book starts as Read, finished today; choosing another status clears that date unless the Reader changed it.
- Choosing Skip while the cover is being found keeps the generated cover.
- Where no cover can be fetched, the generated cover remains.
- Title and author are required; everything else may stay empty.
