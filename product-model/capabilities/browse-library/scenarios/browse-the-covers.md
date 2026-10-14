---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader opens the Library
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::library } }
  - text: "The Product shows every Book as its cover, Reading first, then TBR newest added, then Read most recently finished, then Didn't finish, with the count of volumes, how many are read and the average rating"
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Genre, Rating, Date finished, Cover photo, Binding colour, Added] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The Product shows a progress bar under each Book being read that has a Progress update, and the rating or status under the others
    kind: product
    actor: reader
    entities:
      - { entity: progress-update, effect: reads, facts: [Percentage] }
      - { entity: book, effect: reads, facts: [Rating] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The Reader picks a status chip and types a search
    kind: actor
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Genre] }
    contexts: { web: { place: web::signed-in::library } }
  - text: The shelf narrows to the Books of that status whose title, author or genre contains the search
    kind: condition
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Genre] }
    contexts: { web: { place: web::signed-in::library } }
---

# Browse the covers

## Trigger

The Reader wants to see what is on their shelf.

## Outcome

The Reader sees the matching Books as covers, those on the go first.

## Edge cases

- The library opens on All, so a Book just added always shows.
- The average counts only rated Books read to the end.
