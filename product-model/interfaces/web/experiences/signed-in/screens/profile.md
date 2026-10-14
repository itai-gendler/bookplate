---
entities:
  - { entity: reader, shows: [Name, Email, Profile photo], collects: [Profile photo] }
entryPoints:
  - web: /settings
references:
  - { kind: code, role: implementation, target: app/settings/page.tsx }
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
---

# Profile

The Profile tab of Settings: the reader's name, email and photo, and the way
in to showcasing a year.
