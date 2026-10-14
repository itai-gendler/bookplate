---
entities:
  - { entity: reader, collects: [Password] }
entryPoints:
  - web: /settings?tab=delete
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
---

# Delete account

The Delete account tab of Settings, where a reader deletes their account and
everything in it.
