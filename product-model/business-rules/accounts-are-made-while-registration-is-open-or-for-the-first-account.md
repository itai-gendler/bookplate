---
appliesTo:
  - type: entity
    id: reader
    effect: creates
permits:
  - actors: [visitor]
    when:
      - { entity: server-configuration, fact: Registration, is: Open }
  - actors: [visitor]
    when:
      - { entity: server-configuration, fact: Owner account, absent: true }
references:
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: code, role: implementation, target: lib/config.ts }
  - { kind: doc, role: intent, target: README.md, title: "README: Install with Docker" }
---

# A visitor makes an account only while registration is open, or the server's first one

On a server with registration closed, the default, only the first account, the owner's, can be made. With registration open, anyone who can reach the server makes their own.

## Rationale

A self-hosted Bookplate is one person's library unless its operator chooses to host others.
