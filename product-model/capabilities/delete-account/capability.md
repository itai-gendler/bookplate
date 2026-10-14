---
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: app/api/account/route.ts }
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
---

# Delete account

Permanently delete the account and its whole library, confirmed with the
password.
