---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader opens a Reading Book that has a page count
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Pages] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Reader enters the page they are on and chooses Update
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product records today's Progress update with that page and the percentage it makes
    kind: product
    actor: reader
    entities:
      - { entity: progress-update, effect: creates, facts: [Day, Page, Percentage] }
    contexts: { web: { place: web::signed-in::book-details } }
  - text: The Product shows the percentage read, when the Book was started, how many days it has been read, and once two days are logged the pace and the days left at it
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: progress-update, effect: reads, facts: [Day, Page, Percentage] }
    contexts: { web: { place: web::signed-in::book-details } }
---

# Log the page you are on

## Trigger

The Reader has read some more of a Book.

## Outcome

The Book shows where the Reader is, with a bar on its cover in the Library.

## Edge cases

- The first Progress update marks the day the Book was started.
- The four latest updates are listed, newest first.
- A corrected page count recomputes every update's percentage from its page.
