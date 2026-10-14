---
entities:
  - { entity: book, shows: [Title, Author, Genre, Rating, Date finished, Cover photo, Binding colour, Physical copy] }
  - { entity: progress-update, shows: [Percentage] }
entryPoints:
  - web: /
references:
  - { kind: code, role: implementation, target: app/page.tsx }
  - { kind: code, role: implementation, target: components/Toolbar.tsx }
  - { kind: code, role: implementation, target: components/CoverGrid.tsx }
  - { kind: code, role: implementation, target: components/ListView.tsx }
  - { kind: visual, role: intent, target: docs/covers.png, title: The covers view }
  - { kind: visual, role: intent, target: docs/ledger.png, title: The ledger view }
---

# Library

The reader's shelf, as a grid of covers or as a ledger of every volume, with
the library's totals, a search, status filters and the Show notes marker.
