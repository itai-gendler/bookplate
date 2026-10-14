---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader opens a Reading Book with no page count
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Pages] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product explains that progress is a percentage until a page count is added
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Reader enters the percentage read and chooses Update
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product records today's Progress update with that percentage
    kind: product
    actor: reader
    entities:
      - { entity: progress-update, effect: creates, facts: [Day, Percentage] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Log a percentage

## Trigger

The Reader tracks a Book without a page count, such as an e-book or audiobook.

## Outcome

The Book shows the percentage read.
