---
domain: profile
references:
  - { kind: code, role: implementation, target: lib/showcase.ts }
  - { kind: code, role: implementation, target: lib/showcaseYear.ts }
  - { kind: doc, role: intent, target: README.md, title: "README: Showcase your year" }
---

# Showcase

A public page of one year of a reader's reading, for anyone the reader sends
its link to. It keeps only the reader's choices; the books on it are the
library as it is each time the page is opened.

## Information kept

- **Year** — the year it shows, from 1900 to this one
- **Books to show** — Read and Reading, Read only, or Reading only
- **Name on the page** — the name the page carries, up to 40 characters, or no name
- **Link** — the page's address, long and random, the same for as long as the showcase exists
