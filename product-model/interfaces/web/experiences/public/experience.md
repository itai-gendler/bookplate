---
actors: [visitor]
access: public
entryPoints:
  - web: /login
references:
  - { kind: code, role: implementation, target: proxy.ts }
  - { kind: code, role: implementation, target: components/AuthForm.tsx }
---

# Public pages

Where people arrive without being signed in: to sign in, to set up a new
server's first account, to sign up where registration is open, to reset a
forgotten password, to follow an emailed link, to read the server's privacy
policy and terms, and to open a showcase someone sent them.
