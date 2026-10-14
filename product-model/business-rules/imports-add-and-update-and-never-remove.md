---
appliesTo:
  - { type: capability, id: import-library }
  - { type: capability, id: import-from-goodreads-or-storygraph }
references:
  - { kind: code, role: implementation, target: lib/library.ts#importRecords }
---

# An import adds and updates, and never removes

Records in an import replace those already in the library with the same ids, or the same books; nothing already in the library is ever deleted by an import.
