---
domain: profile
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
  - { kind: code, role: implementation, target: app/api/avatar/route.ts }
---

# Change profile photo

Add a profile photo, or replace the one there, cropped to a circle.
