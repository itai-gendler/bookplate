---
entities:
  - { entity: reader, shows: [Optional features, Newsletter], collects: [Optional features, Newsletter] }
entryPoints:
  - web: /settings?tab=preferences
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
  - { kind: code, role: implementation, target: lib/featureList.ts }
---

# Preferences

The Preferences tab of Settings: the optional book details and, where the
server offers one, the newsletter.
