---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Delete on a Book's details
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product asks whether to remove the Book, naming its title and author
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Reader chooses Remove
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product removes the Book with its Notes page, pasted images, cover and Progress updates
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: removes, from: TBR }
      - { entity: notes-page, effect: removes, with: book }
      - { entity: progress-update, effect: removes, with: book }
    contexts: { web: { place: web::signed-in::library } }
---

# Delete a book

## Trigger

The Reader no longer wants a Book on the shelf.

## Outcome

The Book and everything kept with it are gone; words learned from it stay in the registry.

## Edge cases

- Books are deleted the same way whatever their status.
- Keep it closes the question and keeps the Book.
