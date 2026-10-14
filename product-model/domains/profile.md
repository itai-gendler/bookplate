---
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
  - { kind: code, role: implementation, target: components/ShowcaseDialog.tsx }
---

# Profile

The Profile tab of Settings: the reader's profile photo and the showcases of
their years of reading.

## Boundary

Owns the profile photo and showcases. Does not own the books a showcase
shows, the reader's password or email, or their preferences.
