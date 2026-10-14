---
references:
  - { kind: code, role: implementation, target: app/vocabulary/page.tsx }
---

# Vocabulary

The registry of words learned while reading: looking words up, keeping a
meaning, and browsing and forgetting kept words.

## Boundary

Owns words and the lookups that lead to them. Does not own the books a word
came from; it only points at them.
