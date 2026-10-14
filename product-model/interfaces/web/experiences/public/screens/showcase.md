---
entities:
  - { entity: showcase, shows: [Year, Name on the page] }
  - { entity: book, shows: [Title, Author, Genre, Pages, Rating, Date finished, Cover photo, Binding colour] }
  - { entity: progress-update, shows: [Percentage] }
  - { entity: server-configuration, shows: [Report address, Registration] }
entryPoints:
  - web: "/s/[id]"
references:
  - { kind: code, role: implementation, target: "app/s/[id]/page.tsx" }
  - { kind: code, role: implementation, target: "app/s/[id]/opengraph-image.tsx" }
  - { kind: code, role: implementation, target: lib/showcaseYear.ts#buildShowcaseYear }
---

# Showcase

The public page of one reader's year in books: a bookplate with the name on
it, the year's numbers, each book under the month it was finished, what is on
the nightstand now and the five-star reads, with a picture for link previews.
