---
domain: library
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: "app/books/[id]/page.tsx" }
  - { kind: code, role: implementation, target: components/NotesFormatBar.tsx }
  - { kind: code, role: implementation, target: "app/api/notes/[id]/route.ts" }
  - { kind: code, role: implementation, target: app/api/notes/images/route.ts }
  - { kind: code, role: implementation, target: lib/library.ts#reconcileNotesImages }
  - { kind: code, role: implementation, target: lib/image.ts#compressForNotes }
---

# Edit a book's notes

Write a book's notes in an editor where Markdown renders as it is typed and
pasted images appear inline, then save them or cancel.
