---
kind: primary
routes:
  web: Web
steps:
  - text: The Visitor opens a Showcase link
    kind: actor
    actor: visitor
    entities:
      - { entity: showcase, effect: reads, facts: [] }
    contexts: { web: { place: web::public::showcase } }
  - text: "The Product shows the bookplate with the name on the page, and the year's books read, pages with the pages a day, average rating with the five-star reads, and the longest book"
    kind: product
    actor: visitor
    entities:
      - { entity: showcase, effect: reads, facts: [Year, Name on the page, Books to show] }
      - { entity: book, effect: reads, facts: [Title, Pages, Rating, Date finished] }
    contexts: { web: { place: web::public::showcase } }
  - text: "The Product shows each Book read that year under the month it was finished, the Books on the nightstand now with how far along they are, and the five-star reads, as covers"
    kind: product
    actor: visitor
    entities:
      - { entity: book, effect: reads, facts: [Title, Author, Genre, Cover photo, Binding colour, Rating, Date finished] }
      - { entity: progress-update, effect: reads, facts: [Percentage] }
    contexts: { web: { place: web::public::showcase } }
---

# Open a showcase

## Trigger

Someone sends the Visitor the link to their year in books.

## Outcome

The Visitor sees the reader's year as it stands today.

## Decision points

### Invitation

Is registration open on this server?

- Registration is open → the page invites the Visitor to start their own library
- Registration is closed → the page points to what Bookplate is

## Edge cases

- The page asks search engines not to list it, and its link preview carries a picture of the year.
- With a report address set, the page offers Report this page, which writes to it.
- The reader who owns it, signed in, sees a note pointing to Settings instead of the invitation.
