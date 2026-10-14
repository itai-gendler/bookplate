---
entities:
  - { entity: reader, collects: [Name, Email, Password] }
entryPoints:
  - web: /setup
references:
  - { kind: code, role: implementation, target: app/setup/page.tsx }
---

# Set up your library

The first-run page of a new server, where the account that owns this Bookplate
is made. It exists only until that account does.
