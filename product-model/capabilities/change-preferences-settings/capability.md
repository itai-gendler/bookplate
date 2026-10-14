---
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
  - { kind: code, role: implementation, target: app/api/account/features/route.ts }
  - { kind: code, role: implementation, target: app/api/account/route.ts }
  - { kind: code, role: implementation, target: lib/featureList.ts }
---

# Change preferences settings

Switch the optional book details, Source and Copy, on or off, and on servers
that offer one, the newsletter; each switch saves as it is flipped.
