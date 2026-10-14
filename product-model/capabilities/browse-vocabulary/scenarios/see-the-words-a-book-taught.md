---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader opens a Book's page
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-page } }
  - text: The Product lists under the notes the Words learned from this Book, with the way to look up a new word
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: word, effect: reads, facts: [Word, Part of speech, Definition, Example] }
    contexts: { web: { place: web::signed-in::book-page } }
---

# See the words a book taught

## Trigger

The Reader is on a Book's page and has kept words from it.

## Outcome

The Reader sees that Book's words beside its notes.
