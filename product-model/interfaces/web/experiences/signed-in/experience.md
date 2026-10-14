---
actors: [reader]
access: authenticated
entryPoints:
  - web: /
references:
  - { kind: code, role: implementation, target: lib/auth.ts#requireUser }
  - { kind: code, role: implementation, target: components/AppNav.tsx }
  - { kind: code, role: implementation, target: components/UserMenu.tsx }
---

# Signed in

Where a reader keeps their own library: the Library, Vocabulary and
Statistics sections, each book's notes page, and Settings. Everything here is
the signed-in reader's own.
