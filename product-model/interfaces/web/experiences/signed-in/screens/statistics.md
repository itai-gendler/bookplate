---
entities:
  - { entity: book, shows: [Title, Author, Genre, Pages, Source, Rating, Date finished, Binding colour] }
  - { entity: progress-update, shows: [Day, Percentage] }
entryPoints:
  - web: /statistics
references:
  - { kind: code, role: implementation, target: app/statistics/page.tsx }
  - { kind: code, role: implementation, target: components/StatsView.tsx }
  - { kind: visual, role: intent, target: docs/statistics.png, title: The statistics view }
  - { kind: visual, role: intent, target: docs/drill-down.png, title: Drilling into a year }
---

# Statistics

The shelf counted and charted: totals, what is being read now, books
finished by year, ratings, genres and sources, each open to the books behind
it.
