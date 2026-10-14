---
appliesTo:
  - { type: capability, id: change-preferences-settings }
  - { type: capability, id: edit-book }
  - { type: capability, id: export-library }
references:
  - { kind: code, role: implementation, target: lib/featureList.ts }
  - { kind: code, role: implementation, target: components/BookForm.tsx }
---

# Switching an optional detail off only hides it

A Book's source and copy stay kept, saved back unchanged when the Book is edited and included in exports, while their detail is switched off, and show again when it is switched on.
