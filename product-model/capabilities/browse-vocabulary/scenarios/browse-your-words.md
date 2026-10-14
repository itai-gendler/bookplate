---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader opens Vocabulary
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Product shows how many Words are collected and how many this month, then each Word with its meaning, the Book it came from and the day it was kept, newest first
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [Word, Phonetic spelling, Part of speech, Definition, Example, Synonyms, Kept on] }
      - { entity: book, effect: reads, facts: [Title] }
    contexts: { web: { place: web::signed-in::vocabulary } }
  - text: The Reader searches the words, definitions and examples, narrows to one Book and sorts alphabetically
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: word, effect: reads, facts: [Word, Definition, Example] }
    contexts: { web: { place: web::signed-in::vocabulary } }
---

# Browse your words

## Trigger

The Reader wants to revisit the words they have gathered.

## Outcome

The Reader sees the Words that match, in the order chosen.

## Edge cases

- The book filter lists only Books that have words.
- A word whose card cuts its text short links to its full Wiktionary entry.
- With no words yet the registry invites a first lookup; when nothing matches it says so.
