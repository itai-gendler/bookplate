---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses a zip under Import
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product reads the Books, Words, Progress updates, Notes pages, pasted images and covers in it, skipping anything unreadable
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
      - { entity: progress-update, effect: reads, facts: [] }
      - { entity: notes-page, effect: reads, facts: [] }
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: "The Product stores the images and writes the Books with their Notes pages and Progress updates in one go: those with the ids of records already here replace them, and nothing else is removed"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: creates, to: Read, facts: [Title, Author, Genre, Pages, Source, Physical copy, Rating, Date finished, Cover photo, Binding colour, ISBN, Open Library work, Added, Short note] }
      - { entity: notes-page, effect: creates, with: book, facts: [Text, Pasted images] }
      - { entity: progress-update, effect: creates, with: book, facts: [Day, Page, Percentage] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product writes the Words in the same go, replacing those with the ids of Words already here
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: creates, facts: [Word, Phonetic spelling, Part of speech, Definition, Example, Synonyms, Kept on] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product says how many Books, Words, notes and images were imported and how many unreadable items were skipped
    kind: product
    actor: reader
    entities:
      - { entity: word, effect: reads, facts: [] }
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Import a Bookplate export

## Trigger

The Reader moves a library in, restores a backup or switches image storage.

## Outcome

The library holds everything in the zip alongside what was already there.

## Edge cases

- A zip of the original app's data folder, even inside a top-level folder, imports the same way.
- Books arrive in whatever status the export gave them; a Book with none is TBR.
- A file over the server's largest import, or a zip that unpacks to far more, is refused.
