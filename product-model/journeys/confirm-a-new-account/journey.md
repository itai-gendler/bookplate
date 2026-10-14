---
actors: [visitor]
references:
  - { kind: code, role: implementation, target: components/AuthForm.tsx }
  - { kind: code, role: implementation, target: lib/auth.ts }
---

# Confirm a new account

## Goal

Someone signing up on a server with open registration and email ends up with
a confirmed account, signed in to their new library.

## Success criterion

The account's address is confirmed and its owner is signed in to the library.
