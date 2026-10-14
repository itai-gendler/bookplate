---
domain: security
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
  - { kind: code, role: implementation, target: lib/auth.ts }
---

# Change password

Change the password, knowing the current one, and sign every other device out.
