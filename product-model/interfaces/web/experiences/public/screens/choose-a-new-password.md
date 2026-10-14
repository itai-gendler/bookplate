---
entities:
  - { entity: reader, collects: [Password] }
entryPoints:
  - web: /reset-password
references:
  - { kind: code, role: implementation, target: app/reset-password/page.tsx }
  - { kind: code, role: implementation, target: components/ResetPasswordForm.tsx }
---

# Choose a new password

Where an emailed reset link lands, for choosing the new password.
