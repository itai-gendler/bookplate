---
domain: import-and-export
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: lib/csvImport.ts }
  - { kind: code, role: implementation, target: app/api/import/csv/route.ts }
  - { kind: code, role: implementation, target: components/SettingsPanel.tsx }
---

# Import from Goodreads or StoryGraph

Bring in the books from a Goodreads or StoryGraph CSV export, seeing first
what will happen, with reviews becoming notes pages.
