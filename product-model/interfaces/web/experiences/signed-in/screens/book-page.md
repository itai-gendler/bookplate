---
entities:
  - { entity: book, shows: [Title, Author, Genre, Pages, Rating, Cover photo, Binding colour] }
  - { entity: notes-page, shows: [Text, Pasted images], collects: [Text, Pasted images] }
  - { entity: word, shows: [Word, Part of speech, Definition, Example] }
entryPoints:
  - web: "/books/[id]"
references:
  - { kind: code, role: implementation, target: "app/books/[id]/page.tsx" }
  - { kind: code, role: implementation, target: components/NotesFormatBar.tsx }
---

# Book page

A book's own page: its notes, read and written in place, and the words
learned from it.
