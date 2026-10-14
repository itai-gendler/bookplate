---
domain: vocabulary
references:
  - { kind: code, role: implementation, target: lib/types.ts }
  - { kind: code, role: implementation, target: lib/validate.ts#isValidVocab }
  - { kind: code, role: implementation, target: app/vocabulary/page.tsx }
---

# Word

A word the reader learned while reading, kept in their vocabulary registry
with the one meaning they chose and, optionally, the book it came from.

## Information kept

- **Word** — the word itself
- **Phonetic spelling** — how it is pronounced, where an imported word carries one
- **Part of speech** — noun, verb and so on
- **Definition** — the meaning kept, from the dictionary or in the reader's own words
- **Example** — a sentence using the word
- **Synonyms** — related words, where an imported word carries them
- **Kept on** — when the word was added to the registry
