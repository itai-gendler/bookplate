---
entities:
  - { entity: reader, collects: [Email] }
entryPoints:
  - web: /forgot-password
references:
  - { kind: code, role: implementation, target: app/forgot-password/page.tsx }
  - { kind: code, role: implementation, target: components/ForgotPasswordForm.tsx }
---

# Forgot your password?

Where a reader who has forgotten their password asks for a reset link, or,
on a server that can't send email, learns how whoever runs it resets one.
