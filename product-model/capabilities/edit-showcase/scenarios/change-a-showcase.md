---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader picks a year marked shared in Showcase your year
    kind: actor
    actor: reader
    entities:
      - { entity: showcase, effect: reads, facts: [] }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Product shows that Showcase's choices and its link
    kind: product
    actor: reader
    entities:
      - { entity: showcase, effect: reads, facts: [Year, Books to show, Name on the page, Link] }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Reader changes what the page shows or the name on it and chooses Save changes
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Product saves the choices and keeps the same link
    kind: product
    actor: reader
    entities:
      - { entity: showcase, effect: changes, facts: [Books to show, Name on the page] }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
---

# Change a showcase

## Trigger

The Reader wants their shared page to show something different.

## Outcome

The page shows the new choices at the link already sent.

## Edge cases

- Save changes is offered only once something differs from what is saved.
