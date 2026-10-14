---
domain: profile
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/ShowcaseDialog.tsx }
  - { kind: code, role: implementation, target: "app/api/showcases/[id]/route.ts" }
---

# Turn off a showcase

Stop sharing a year: the showcase is deleted and its link stops working.
