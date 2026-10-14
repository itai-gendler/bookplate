---
appliesTo:
  - { type: capability, id: import-from-goodreads-or-storygraph }
  - { type: entity, id: book, facts: [ISBN] }
references:
  - { kind: code, role: implementation, target: lib/csvImport.ts }
---

# Importing the same export again updates the books it brought in

Each row is matched to a Book already in the library by the id an earlier import gave it, then its ISBN, then its title and author, and that Book is updated in place, keeping its cover, colour, genre, source and notes.
