---
domain: library
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: "app/books/[id]/page.tsx" }
  - { kind: code, role: implementation, target: "app/api/notes/[id]/route.ts" }
---

# Read a book's notes

Open a book's own page to read its notes, with the words learned from it.
