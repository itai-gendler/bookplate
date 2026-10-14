---
appliesTo:
  - type: entity
    id: book
    effect: reads
    facts: [Source, Physical copy, Short note]
    contexts: [{ place: web::public::showcase }]
  - type: entity
    id: notes-page
    effect: reads
    contexts: [{ place: web::public::showcase }]
  - type: entity
    id: word
    effect: reads
    contexts: [{ place: web::public::showcase }]
permits: []
references:
  - { kind: code, role: implementation, target: lib/showcase.ts }
  - { kind: doc, role: intent, target: README.md, title: "README: Showcase your year" }
---

# A showcase never shows notes, words, sources or copies

A Showcase shows covers, titles, authors, ratings and page counts. A Book's notes, the Words learned from it, its source and whether a copy is owned never appear on it, for anyone.
