---
domain: library
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/ProgressPanel.tsx }
  - { kind: code, role: implementation, target: lib/progress.ts }
  - { kind: code, role: implementation, target: "app/api/progress/[bookId]/route.ts" }
  - { kind: code, role: implementation, target: lib/validate.ts#isValidProgress }
---

# Log reading progress

Record where the reader has got to in a book they are reading, as a page or a
percentage, and see their pace and how long is left.
