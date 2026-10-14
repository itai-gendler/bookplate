---
domain: import-and-export
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
  - { kind: code, role: implementation, target: app/api/covers/lookup/route.ts }
  - { kind: code, role: implementation, target: lib/coverLookup.ts#findCover }
  - { kind: code, role: implementation, target: lib/outbound.ts }
---

# Find covers

Look up covers for books just imported, one book every few seconds, while the
page stays open.
