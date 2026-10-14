---
domain: library
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/BookForm.tsx }
  - { kind: code, role: implementation, target: app/page.tsx }
  - { kind: code, role: implementation, target: "app/api/books/[id]/route.ts" }
  - { kind: code, role: implementation, target: app/api/booksearch/route.ts }
  - { kind: code, role: implementation, target: app/api/booksearch/cover/route.ts }
  - { kind: code, role: implementation, target: app/api/covers/route.ts }
  - { kind: doc, role: intent, target: README.md, title: "README: Adding books and Cover images" }
---

# Add a book

Put a new book on the shelf, its details found in the Open Library catalogue
or entered by hand, with a cover fetched from the catalogue, uploaded or pasted
and cropped to book proportions, or a generated cloth cover.
