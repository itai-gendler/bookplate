---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses a Goodreads or StoryGraph CSV export
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: "The Product recognises which service it came from and, saving nothing, says how many books it holds by status, how many are new and how many already here would be updated, how many reviews become notes pages and how many rows lack a title or author"
    kind: product
    actor: reader
    entities:
      - { entity: notes-page, effect: reads, facts: [] }
      - { entity: book, effect: reads, facts: [Title, Author, ISBN] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Reader chooses Import
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: "The Product adds each Book with its shelf as status, rating to the half star, dates, ISBN, page count, format as source and owned copies, and turns its review and private notes into its Notes page"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: creates, to: TBR, facts: [Title, Author, ISBN, Pages, Rating, Date finished, Source, Physical copy, Binding colour, Added] }
      - { entity: notes-page, effect: creates, with: book, facts: [Text] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product says how many Books were imported and offers to find covers for those without one
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Import a Goodreads export

## Trigger

The Reader moves their reading history from Goodreads or StoryGraph.

## Outcome

The Books are on the shelf, with generated covers until covers are found.

## Edge cases

- Goodreads series suffixes are dropped from titles.
- A Goodreads shelf named like dnf or did-not-finish becomes Didn't finish; other custom shelves become TBR.
- Cancel discards the preview and saves nothing.
- The same book twice in one file is imported once.
