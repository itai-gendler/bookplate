---
kind: alternative
routes:
  web: Web
steps:
  - text: Having looked a word up, the Reader chooses to write their own definition
    kind: actor
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Reader enters the definition, and optionally the part of speech and the sentence where they met it, and chooses Keep this word
    kind: actor
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product keeps the Word with the Reader's own definition, tagged with the Book chosen
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: word, effect: creates, facts: [Word, Part of speech, Definition, Example, Kept on] }
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Keep a word in your own words

## Trigger

The dictionary has no entry, or none of its senses fits.

## Outcome

The Word is in the registry with the Reader's definition.

## Edge cases

- Keep this word stays unavailable until a definition is written.
