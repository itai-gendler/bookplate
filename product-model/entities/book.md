---
domain: library
relations:
  - entity: notes-page
    verb: has
    cardinality: one-to-one
  - entity: progress-update
    verb: has
    cardinality: one-to-many
  - entity: word
    verb: taught
    cardinality: one-to-many
references:
  - { kind: code, role: implementation, target: lib/types.ts }
  - { kind: code, role: implementation, target: lib/db/schema.ts }
  - { kind: code, role: implementation, target: lib/library.ts }
  - { kind: code, role: implementation, target: lib/validate.ts#isValidBook }
  - { kind: code, role: implementation, target: lib/palette.ts }
---

# Book

One volume in a reader's library, with its reading status, its details and
its cover.

## Information kept

- **Title** — the book's title; required
- **Author** — the book's author; required
- **Genre** — a category chosen from those already in the library or typed new
- **Pages** — the page count, when known
- **Source** — where the book came from: Book store, Kindle, Audiobook, Borrowed, Second hand, Gifted, Library or a source the reader typed
- **Physical copy** — whether the reader owns a physical copy at home
- **Rating** — zero to five stars in half-star steps; zero is not yet rated
- **Date finished** — the day the book was finished, or for a book the reader didn't finish, the day they stopped
- **Cover photo** — a cropped cover image; without one the book wears a generated cloth cover
- **Binding colour** — one of twelve cloth colours for the generated cover, picked at random when the book is added
- **ISBN** — the book's ISBN, brought in by a Goodreads or StoryGraph import and used to find its cover
- **Open Library work** — the catalogue work the book was picked from, when added from the catalogue
- **Added** — when the book joined the library
- **Short note** — a one-line note kept from before books had notes pages

## States

### Read

The reader has read the book to the end. Its Date finished is when they
finished it.

### Reading

The reader is reading the book now and can log their progress through it.

### TBR

The book is waiting to be read.

### Didn't finish

The reader gave the book up. Its Date finished is when they stopped.
