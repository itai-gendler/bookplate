---
domain: library
references:
  - { kind: code, role: implementation, target: lib/progress.ts }
  - { kind: code, role: implementation, target: lib/db/schema.ts }
  - { kind: code, role: implementation, target: "app/api/progress/[bookId]/route.ts" }
---

# Progress update

Where the reader had got to in a book they are reading on one day. The first
update marks when the book was started; together the updates give the reader's
pace and how long is left.

## Information kept

- **Day** — the reader's own calendar day the update is for
- **Page** — the page reached, for a book with a page count
- **Percentage** — how much of the book is read, from 0 to 100
