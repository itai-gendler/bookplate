---
domain: library
references:
  - { kind: code, role: implementation, target: lib/library.ts#writeNotes }
  - { kind: code, role: implementation, target: "app/books/[id]/page.tsx" }
  - { kind: doc, role: intent, target: README.md, title: "README: A notes page per book" }
---

# Notes page

The reader's notes on one book, written on the book's own page and kept as
Markdown with the images pasted into them.

## Information kept

- **Text** — the notes, with headings, emphasis, lists, quotes and callouts
- **Pasted images** — the images pasted or dropped into the notes, shown where they were placed
