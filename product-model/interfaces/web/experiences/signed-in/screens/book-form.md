---
entities:
  - { entity: book, shows: [Title, Author, Genre, Pages, Source, Physical copy, Rating, Date finished, Cover photo], collects: [Title, Author, Genre, Pages, Source, Physical copy, Rating, Date finished, Cover photo] }
references:
  - { kind: code, role: implementation, target: components/BookForm.tsx }
  - { kind: code, role: implementation, target: components/ImageCropper.tsx }
  - { kind: visual, role: intent, target: docs/add-book.png, title: Adding a book via catalogue search }
---

# Add or edit a book

The form for adding a book or changing one: a catalogue search that fills the
details, the details themselves, and a cover found, uploaded or pasted and
cropped to book proportions.
