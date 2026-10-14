---
appliesTo:
  - { type: capability, id: log-reading-progress }
  - { type: entity, id: progress-update }
references:
  - { kind: code, role: implementation, target: "app/api/progress/[bookId]/route.ts" }
  - { kind: code, role: implementation, target: lib/validate.ts#isValidProgress }
---

# A logged page is never past the book's last page

A Progress update's page is from 0 to the Book's page count, and its percentage from 0 to 100.
