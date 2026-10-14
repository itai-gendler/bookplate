---
domain: library
availability:
  - { place: web::signed-in }
references:
  - { kind: code, role: implementation, target: components/ProgressPanel.tsx }
  - { kind: code, role: implementation, target: lib/library.ts#deleteProgress }
---

# Remove a progress update

Undo a mistaken day's update on a book being read.
