---
domain: library
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/BookForm.tsx }
  - { kind: code, role: implementation, target: app/page.tsx }
  - { kind: code, role: implementation, target: "app/api/books/[id]/route.ts" }
  - { kind: code, role: implementation, target: "app/api/covers/[name]/route.ts" }
---

# Edit a book

Change a book's details, its status and its cover from the same form it was
added with.
