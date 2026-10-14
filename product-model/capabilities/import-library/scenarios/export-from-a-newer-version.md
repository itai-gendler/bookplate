---
kind: validation
routes:
  web: Web
steps:
  - text: The Reader imports a zip made by a newer version of Bookplate
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
  - text: The Product imports nothing and says to update this server first
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::import-and-export } }
---

# Export from a newer version

## Trigger

The Reader brings an export from a Bookplate newer than this server.

## Outcome

The library is unchanged.

## Edge cases

- A file that is not a readable zip, or holds no library, is refused the same way with its own message.
