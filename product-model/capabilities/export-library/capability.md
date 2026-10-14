---
domain: import-and-export
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: lib/archive.ts#buildExport }
  - { kind: code, role: implementation, target: app/api/export/route.ts }
  - { kind: doc, role: intent, target: README.md, title: "README: Backups" }
---

# Export library

Download the whole library as one zip of plain JSON, Markdown and image files,
readable without Bookplate and importable into any Bookplate.
