---
kind: primary
routes:
  cli: Server commands
steps:
  - text: The Server operator runs reset-password with the account's email
    kind: actor
    actor: server-operator
    entities: []
    contexts: { cli: { place: server-commands } }
  - text: The Server operator types the new password twice without it showing
    kind: actor
    actor: server-operator
    entities: []
    contexts: { cli: { place: server-commands } }
  - text: The Product changes that account's password and signs out every device
    kind: product
    actor: server-operator
    entities:
      - { entity: reader, effect: changes, facts: [Password] }
    contexts: { cli: { place: server-commands } }
---

# Reset a password on the server

## Trigger

A reader has forgotten their password and the server has no email, or they can't reach their inbox.

## Outcome

The reader signs in with the new password.

## Edge cases

- An address with no account, two passwords that differ, or one outside 8 to 128 characters changes nothing.
- It does not count the address as confirmed.
