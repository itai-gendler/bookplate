---
references:
  - { kind: code, role: implementation, target: app/page.tsx }
  - { kind: code, role: implementation, target: components/AppNav.tsx }
---

# Library

The reader's shelf: the books, their details, statuses and covers, the
progress logged while reading them, and each book's notes page.

## Boundary

Owns books, their notes pages and their progress updates. Does not own the
words learned from a book, which belong to Vocabulary, the statistics drawn
from the shelf, or the public showcase of a year's reading.
