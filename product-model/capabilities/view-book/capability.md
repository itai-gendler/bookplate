---
domain: library
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/BookDetail.tsx }
  - { kind: code, role: implementation, target: lib/progress.ts#summarize }
  - { kind: code, role: implementation, target: app/statistics/page.tsx }
---

# View a book

Open one book's details: its cover, status, rating, details and whether it
has notes, with how long it took to read where its reading was tracked.
