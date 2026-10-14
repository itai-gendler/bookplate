---
appliesTo:
  - { type: capability, id: edit-book-notes }
  - { type: entity, id: notes-page }
references:
  - { kind: code, role: implementation, target: lib/library.ts#reconcileNotesImages }
---

# Notes keep only the images their text uses

Every save deletes the stored images the notes no longer show, and Cancel deletes the images pasted since the last save.
