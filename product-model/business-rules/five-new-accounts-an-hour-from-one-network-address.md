---
appliesTo:
  - { type: capability, id: create-account }
  - { type: entity, id: reader }
references:
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: doc, role: intent, target: README.md, title: "README: Open registration" }
---

# At most five new accounts an hour come from one network address

Beyond five accounts made from one address in an hour, sign-up asks the visitor to try again in an hour.

## Rationale

With registration open, this slows anyone making accounts in bulk.
