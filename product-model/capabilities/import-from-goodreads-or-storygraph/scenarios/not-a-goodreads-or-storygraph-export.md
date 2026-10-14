---
kind: validation
routes:
  web: Web
steps:
  - text: The Reader chooses a CSV that is not a Goodreads or StoryGraph export
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product saves nothing and says no matching columns were found
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Not a Goodreads or StoryGraph export

## Trigger

The Reader picks the wrong file.

## Outcome

The library is unchanged.

## Edge cases

- An export with more new books than the server's book limit allows is refused at the preview, before anything is saved.
