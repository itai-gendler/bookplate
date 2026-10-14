---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader picks a shared year and chooses Turn off
    kind: actor
    actor: reader
    entities:
      - { entity: showcase, effect: reads, facts: [Year] }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
  - text: The Product deletes the Showcase, and its link stops working at once
    kind: product
    actor: reader
    entities:
      - { entity: showcase, effect: removes }
    contexts: { web: { place: web::signed-in::showcase-your-year } }
---

# Turn off a showcase

## Trigger

The Reader no longer wants a year shared.

## Outcome

Nobody can open the page any more; making the year again gives a new link.
