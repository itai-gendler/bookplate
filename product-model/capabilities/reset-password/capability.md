---
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: app/forgot-password/page.tsx }
  - { kind: code, role: implementation, target: components/ForgotPasswordForm.tsx }
  - { kind: code, role: implementation, target: app/reset-password/page.tsx }
  - { kind: code, role: implementation, target: components/ResetPasswordForm.tsx }
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: doc, role: intent, target: README.md, title: "README: Forgotten passwords" }
---

# Reset password

Choose a new password after forgetting the old one, through an emailed link,
or learn how the server's operator resets it where the server has no email.
