---
entities:
  - { entity: reader, shows: [Email], collects: [Password] }
entryPoints:
  - web: /settings?tab=security
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
---

# Security

The Security tab of Settings: changing the password and whether the server
can send email.
