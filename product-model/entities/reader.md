---
kind: person
acts: external
relations:
  - entity: book
    verb: owns
    cardinality: one-to-many
  - entity: word
    verb: owns
    cardinality: one-to-many
  - entity: showcase
    verb: owns
    cardinality: one-to-many
references:
  - { kind: code, role: implementation, target: lib/db/schema.ts }
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: code, role: implementation, target: lib/features.ts }
  - { kind: code, role: implementation, target: lib/hints.ts }
---

# Reader

A person signed in to Bookplate with their own account and their own library.
On a server with registration closed there is one reader, the owner who set
it up; with registration open, everyone who signs up is a reader of their own
separate library.

## Information kept

- **Name** — the name given when the account was made, shown in the account menu and offered for a showcase
- **Email** — the address the reader signs in with and receives Bookplate's emails at
- **Password** — the secret the reader signs in with, at least eight characters
- **Profile photo** — a round photo shown in the account menu; without one a default bookshelf picture shows
- **Email confirmed** — whether the reader has confirmed their address through an emailed link
- **Optional features** — which optional book details the reader has switched on: Source and Copy
- **Newsletter** — whether, and since when, the reader asked for the newsletter
- **Dismissed hints** — the explanations the reader chose not to see again
