---
kind: primary
routes:
  web: Web
steps:
  - text: The Reader chooses Delete account, enters their password and chooses Delete my account and library
    kind: actor
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::delete-account } }
  - text: "The Product deletes the account with everything in it: every Book with its Notes page, pasted images, cover and Progress updates, every Word and Showcase, and the profile photo"
    kind: product
    actor: reader
    entities:
      - { entity: reader, effect: removes }
      - { entity: book, effect: removes, from: Read, with: reader }
      - { entity: notes-page, effect: removes, with: book }
      - { entity: progress-update, effect: removes, with: book }
      - { entity: word, effect: removes, with: reader }
      - { entity: showcase, effect: removes, with: reader }
    contexts: { web: { place: web::signed-in::delete-account } }
  - text: The Product shows Sign in
    kind: product
    actor: reader
    entities: []
    contexts: { web: { place: web::signed-in::delete-account } }
---

# Delete your account

## Trigger

The Reader is leaving Bookplate.

## Outcome

The account and its library are gone for good; the address could sign up again.

## Edge cases

- The page suggests exporting the library first, since nothing can be undone.
- Books go whatever their status.
