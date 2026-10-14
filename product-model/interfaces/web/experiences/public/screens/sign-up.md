---
entities:
  - { entity: reader, collects: [Name, Email, Password, Newsletter] }
entryPoints:
  - web: /signup
references:
  - { kind: code, role: implementation, target: app/signup/page.tsx }
  - { kind: code, role: implementation, target: components/AuthForm.tsx }
---

# Create an account

Where anyone who can reach a server with open registration makes their own
account and library.
