---
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: app/signup/page.tsx }
  - { kind: code, role: implementation, target: components/AuthForm.tsx }
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: code, role: implementation, target: lib/botCheck.ts }
  - { kind: code, role: implementation, target: lib/housekeeping.ts#removeUnverifiedAccounts }
  - { kind: doc, role: intent, target: README.md, title: "README: Open registration" }
---

# Create account

Sign up for an account and a library of one's own, on a server whose
registration is open.
