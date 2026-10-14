---
entities:
  - { entity: book, shows: [Title, Author, Genre, Pages, Source, Physical copy, Rating, Date finished, Cover photo, Binding colour], collects: [Date finished, Rating] }
  - { entity: progress-update, shows: [Day, Page, Percentage], collects: [Page, Percentage] }
references:
  - { kind: code, role: implementation, target: components/BookDetail.tsx }
  - { kind: code, role: implementation, target: components/ProgressPanel.tsx }
  - { kind: code, role: implementation, target: components/FinishDialog.tsx }
  - { kind: visual, role: intent, target: docs/detail.png, title: The book detail dialog }
---

# Book details

One book: its cover, status, rating and details, how long it took or how the
reading is going, and the ways to finish it, open its notes, edit or delete
it.
