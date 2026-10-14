---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader opens the account menu and chooses Sign out
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in } }
  - text: The Product ends the session on this device and shows Sign in
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in } }
---

# Sign out of Bookplate

## Trigger

The Reader is done on a device.

## Outcome

The device is signed out; other devices stay signed in.
