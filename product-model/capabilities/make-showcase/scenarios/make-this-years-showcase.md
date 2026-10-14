---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader opens the year dialog from Profile
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::profile } }
  - text: The Product opens on this year, showing Read and Reading, with the Reader's first name as the name on the page
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: reads, facts: [Name] }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Reader keeps or changes what to show and the name, and chooses Make my link
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Product makes the Showcase with a long random link and shows the link to copy or open
    kind: product
    actor: reader
    entities:
      - { entity: showcase, effect: creates, facts: [Year, Books to show, Name on the page, Link] }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
---

# Make this year's showcase

## Trigger

The Reader wants to share their year of reading so far.

## Outcome

The Reader has a link to a page of this year's books that keeps up as they read.

## Edge cases

- An empty name makes a page with no name on it.
- The name is kept to one line of at most 40 characters.
