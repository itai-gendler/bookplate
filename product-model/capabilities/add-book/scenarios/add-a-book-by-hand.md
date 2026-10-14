---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader chooses Add book
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The Reader types the title and author, picks TBR and chooses Add to shelf
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product adds the Book as TBR, wearing a generated cloth cover in a random binding colour
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: creates, to: TBR, facts: [Title, Author, Binding colour, Added] }
    contexts: { web: { place: web::signed-in::library } }
---

# Add a book by hand

## Trigger

The Reader wants a book on the shelf without searching for it.

## Outcome

The Book is on the shelf as TBR with a generated cover.

## Edge cases

- A genre or source not in the list can be typed in as a new one.
