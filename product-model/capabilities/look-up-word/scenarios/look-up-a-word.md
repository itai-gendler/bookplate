---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader types a word they just met, optionally picks the Book it came from, and chooses Look up
    kind: actor
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
      - { entity: book, effect: reads, facts: [Title] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product asks Wiktionary for the word as a lowercase headword, then as typed, and lists up to ten English senses with part of speech and example
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product marks the word as already in the registry when a kept Word has the same spelling
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [Word] }
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Look up a word

## Trigger

The Reader meets a word they don't know.

## Outcome

The Reader sees what it means, sense by sense, ready to keep one.

## Edge cases

- The results close with Escape or a click outside them, except while the Reader is writing a definition of their own.
