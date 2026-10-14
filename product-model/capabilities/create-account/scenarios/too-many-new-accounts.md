---
kind: validation
routes:
  web: Web
steps:
  - text: The Visitor chooses Create account
    kind: actor
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-up } }
  - text: Five accounts have already been made from the Visitor's network address in the last hour
    kind: condition
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-up } }
  - text: The Product makes no account and says there were too many new accounts from the Visitor's network, to try again in an hour
    kind: product
    actor: visitor
    entities: []
    contexts: { web: { place: web::public::sign-up } }
---

# Too many new accounts

## Trigger

Many accounts are being made from one place.

## Outcome

No account is made for now.

## Edge cases

- A failed invisible check is refused the same way, asking the Visitor to reload the page and try again.
