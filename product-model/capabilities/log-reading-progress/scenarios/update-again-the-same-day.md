---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader logs progress on a Book that already has an update for today
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product replaces today's Progress update with the new page and percentage
    kind: product
    actor: reader
    entities:
      - { entity: progress-update, effect: changes, facts: [Page, Percentage] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Update again the same day

## Trigger

The Reader reads more on a day they already logged.

## Outcome

The Book keeps one update for the day, the latest.
