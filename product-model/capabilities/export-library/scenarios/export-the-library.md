---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Export library
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product downloads a zip of the Books, Words and Progress updates as JSON, each Notes page as Markdown with its pasted images, and the covers
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Genre, Pages, Source, Physical copy, Rating, Date finished, Cover photo, Binding colour, ISBN, Open Library work, Added, Short note] }
      - { entity: word, effect: reads, facts: [Word, Phonetic spelling, Part of speech, Definition, Example, Synonyms, Kept on] }
      - { entity: progress-update, effect: reads, facts: [Day, Page, Percentage] }
      - { entity: notes-page, effect: reads, facts: [Text, Pasted images] }
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Export the library

## Trigger

The Reader wants a backup, or to move their library to another Bookplate.

## Outcome

The Reader has a dated zip holding everything in their library.

## Edge cases

- The profile photo and showcases are not in the export.
- Hidden optional details are in the export.
