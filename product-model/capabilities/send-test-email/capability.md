---
domain: security
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: app/api/email/test/route.ts }
  - { kind: code, role: implementation, target: lib/email.ts }
---

# Send test email

Check that the server's email works by sending a test email to oneself.
