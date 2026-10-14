---
references:
  - { kind: code, role: implementation, target: lib/archive.ts }
  - { kind: code, role: implementation, target: lib/csvImport.ts }
---

# Import & export

The Import & export tab of Settings: the library leaving as one zip, and
coming in from a Bookplate export or a Goodreads or StoryGraph CSV.

## Boundary

Owns moving whole libraries in and out and finding covers for imported books.
Does not own adding, editing or deleting one book, which belongs to Library.
