---
id: bookplate
summary: A self-hosted personal reading tracker that keeps books with their status, rating, dates, progress and notes, real or generated covers, and a registry of words learned while reading.
category: reading-tracker
tags: [reading-tracker, books, vocabulary, self-hosted, open-source]
authors:
  - name: Bookplate contributors
    url: https://github.com/LeoPhh/bookplate
license: Apache-2.0
languages: [en]
limitations:
  - Every account keeps its own separate library; nothing in it is shared with anyone except a showcase its reader chooses to make.
  - With registration closed, the default, a server holds one account, its owner's, made on the first visit.
  - Without email set up, a forgotten password is reset by whoever runs the server.
  - The only outside services are Open Library and iTunes for books and covers and Wiktionary for words, reached through Bookplate itself and only when a reader uses those features; nothing external is required.
  - A showcase shows covers, titles, authors, ratings and page counts, never notes, words, sources or copies.
references:
  - { kind: doc, role: intent, target: README.md, title: README }
  - { kind: doc, role: context, target: AGENTS.md, title: "Agent notes on data, auth and styling" }
---

# Bookplate

Bookplate is a personal reading tracker that a reader runs on their own
machine or server. Each book carries its status (read, reading, TBR or didn't
finish), a rating in half stars, the date it was finished or given up, the
reader's progress through it, and a notes page of its own. Books wear a real
cover found in the Open Library catalogue, uploaded or pasted, or a generated
cloth cover. A vocabulary registry keeps the words learned along the way,
looked up in Wiktionary and tied to the book they came from. The library can
be browsed as covers or as a ledger, counted on a statistics page, shared one
year at a time as a public showcase, and exported or imported whole.

## Intent

In the project's own words: "A personal reading tracker with a bold editorial
look." It is self-hosted so that "your library never leaves it", and
"everything can be exported at any time as a zip of plain JSON, markdown and
image files." A server can stay a single reader's library or open registration
so anyone who can reach it keeps a separate library of their own.
