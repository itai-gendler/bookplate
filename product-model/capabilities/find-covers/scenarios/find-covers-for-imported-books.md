---
kind: primary
routes:
  web: Web
steps:
  - text: After an import, the Reader chooses Find covers, told roughly how many minutes it will take
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: For each imported Book without a cover, one every few seconds, the Product looks on Open Library by ISBN, then on iTunes by title and author
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [ISBN, Title, Author] }
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product stores each cover it finds on its Book and counts how many it has done and found
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: changes, facts: [Cover photo] }
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Find covers for imported books

## Trigger

The Reader's imported Books are wearing generated covers.

## Outcome

Books with a cover found wear it; the others keep their cloth cover.

## Edge cases

- When the server is already asking the services for others, it waits its turn and carries on.
- A cover is matched on iTunes only when the title and the author's surname agree.
