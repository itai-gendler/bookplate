---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader switches on Source or Copy
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::preferences } }
  - text: The Product saves the choice on the account, and the detail appears in the book form and details, with a Ledger column for Copy and a Statistics chart for Source
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: reader, effect: changes, facts: [Optional features] }
    contexts: { web: { place: web::signed-in::preferences } }
---

# Switch on an optional detail

## Trigger

The Reader wants to record where their books come from, or which they own.

## Outcome

The detail is kept and shown for every Book from then on.

## Edge cases

- If saving fails the switch flips back and says so.
