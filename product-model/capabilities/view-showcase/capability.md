---
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: "app/s/[id]/page.tsx" }
  - { kind: code, role: implementation, target: "app/s/[id]/covers/[name]/route.ts" }
  - { kind: code, role: implementation, target: lib/showcase.ts#loadShowcase }
  - { kind: code, role: implementation, target: lib/showcaseYear.ts#buildShowcaseYear }
---

# View a showcase

Open a reader's public page of a year in books from the link they sent.
