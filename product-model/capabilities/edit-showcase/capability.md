---
domain: profile
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/ShowcaseDialog.tsx }
  - { kind: code, role: implementation, target: lib/showcase.ts#saveShowcase }
---

# Edit a showcase

Change which books a year's showcase shows or the name on it, keeping its link.
