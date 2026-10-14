---
appliesTo:
  - { type: capability, id: log-reading-progress }
  - { type: entity, id: progress-update }
references:
  - { kind: code, role: implementation, target: lib/library.ts#upsertProgress }
---

# A book keeps one progress update per day

A second update on the same day replaces the first. Days are the Reader's own calendar days.
