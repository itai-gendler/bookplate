---
kind: alternative
routes:
  web: Web
steps:
  - text: The Reader picks an earlier year with finished reading in it
    kind: actor
    actor: reader
    entities:
      - { entity: showcase, effect: reads, facts: [Year] }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Product allows only Read only for a past year, saying only this year's page can show what is being read now
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Reader chooses Make my link
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Product makes that year's Showcase of the books read
    kind: product
    actor: reader
    entities:
      - { entity: book, effect: reads, facts: [] }
      - { entity: showcase, effect: creates, facts: [Year, Books to show, Name on the page, Link] }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
---

# Make a past year's showcase

## Trigger

The Reader wants to share a year that is over.

## Outcome

The Reader has a link to that year's books, by the month each was finished.

## Edge cases

- The years offered are this one and every year with a finished Book.
