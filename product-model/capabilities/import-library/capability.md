---
domain: import-and-export
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: lib/archive.ts#importArchive }
  - { kind: code, role: implementation, target: app/api/import/route.ts }
  - { kind: code, role: implementation, target: lib/library.ts#importRecords }
---

# Import library

Bring a Bookplate export, or a zip of the original app's data folder, into the
library, adding and updating without removing anything.
