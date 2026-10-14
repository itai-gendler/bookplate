---
domain: profile
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/ShowcaseDialog.tsx }
  - { kind: code, role: implementation, target: lib/showcase.ts#parseShowcase }
  - { kind: code, role: implementation, target: lib/showcase.ts#saveShowcase }
  - { kind: code, role: implementation, target: app/settings/page.tsx }
  - { kind: doc, role: intent, target: README.md, title: "README: Showcase your year" }
---

# Make a showcase

Make the public page of one year's reading and get its link to send.
