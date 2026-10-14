---
entities:
  - { entity: word, shows: [Word, Phonetic spelling, Part of speech, Definition, Example, Synonyms, Kept on], collects: [Word, Part of speech, Definition, Example] }
  - { entity: book, shows: [Title] }
entryPoints:
  - web: /vocabulary
references:
  - { kind: code, role: implementation, target: app/vocabulary/page.tsx }
  - { kind: code, role: implementation, target: components/VocabCard.tsx }
---

# Vocabulary

The word registry: a lookup for a word just met and the book it came from,
and every kept word, to search, sort and filter by book.
