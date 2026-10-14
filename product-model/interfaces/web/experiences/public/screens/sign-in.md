---
entities:
  - { entity: reader, collects: [Email, Password] }
entryPoints:
  - web: /login
references:
  - { kind: code, role: implementation, target: app/login/page.tsx }
  - { kind: code, role: implementation, target: components/AuthForm.tsx }
---

# Sign in

Where a reader signs in with their email and password, with the way to a
forgotten password and, where registration is open, to sign-up.
