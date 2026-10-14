---
appliesTo:
  - { type: capability, id: add-book }
  - { type: capability, id: import-library }
  - { type: capability, id: import-from-goodreads-or-storygraph }
  - { type: entity, id: server-configuration, facts: [Book limit] }
references:
  - { kind: code, role: implementation, target: lib/limits.ts }
---

# A library never holds more books than the server's book limit

Where the server sets a book limit, adding or importing past it is refused with the limit named. Books already in the library count as updates, not additions.

## Rationale

On a server where strangers can sign up, one account must not fill the server.
