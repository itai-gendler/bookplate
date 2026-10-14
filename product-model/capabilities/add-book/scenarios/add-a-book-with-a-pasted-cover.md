---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader chooses Add book and enters the title and author
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Reader pastes an image anywhere in the form, or uploads one
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product opens the image to crop to book proportions
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Reader crops it, picks Reading and chooses Add to shelf
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::book-form } }
  - text: The Product stores the cover, compressed to at most 600 by 900, and adds the Book as Reading
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: creates, to: Reading, facts: [Title, Author, Cover photo, Binding colour, Added] }
    contexts: { web: { place: web::signed-in::library } }
---

# Add a book with a pasted cover

## Trigger

The Reader has a picture of the cover at hand.

## Outcome

The Book is on the shelf as Reading, wearing the cropped picture.

## Edge cases

- An image the browser cannot read is refused with a message and the form stays as it was.
- A cover larger than the server's largest image, or beyond the account's image space, is not stored; the Book is still added with the generated cover and the reason is shown.
