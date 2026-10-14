---
kind: primary
routes:
  web: Web
steps:
  - text: Having looked a word up, the Reader chooses Keep on the sense that fits
    kind: actor
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
      - { entity: book, effect: reads, facts: [Title] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product keeps the Word with that sense's part of speech, definition and example, tagged with the Book chosen, and marks the sense Kept
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: word, effect: creates, facts: [Word, Part of speech, Definition, Example, Kept on] }
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Keep a dictionary sense

## Trigger

The Reader has found the meaning they met in their book.

## Outcome

The Word is in the registry, newest first.

## Edge cases

- More than one sense of the same word can be kept, each as its own Word.
- The Book is optional; a word kept with no book shows only the day it was kept.
