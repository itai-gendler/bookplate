---
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: code, role: implementation, target: app/login/page.tsx }
  - { kind: code, role: implementation, target: lib/email.ts#verifyEmail }
---

# Confirm email address

Confirm a new account's address through the emailed link, which also signs
the reader in.
