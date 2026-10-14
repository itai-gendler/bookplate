---
appliesTo:
  - { type: capability, id: reset-password }
  - { type: capability, id: create-account }
references:
  - { kind: code, role: implementation, target: lib/auth.ts }
  - { kind: doc, role: context, target: AGENTS.md, title: Agent notes }
---

# Asking for a reset link or signing up never reveals whether an address has an account

The answer is the same whether or not the address has an account, and a failure to send those emails is never shown to the visitor.
