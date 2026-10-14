---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses to remove one of a Book's recent Progress updates
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: progress-update, effect: reads, facts: [Day, Page, Percentage] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product removes that day's Progress update and works out the progress, start and pace again from the rest
    kind: product
    actor: reader
    entities:
      - { entity: progress-update, effect: removes }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Remove an update

## Trigger

The Reader logged the wrong progress.

## Outcome

The update is gone and the Book's progress reflects the ones left.
