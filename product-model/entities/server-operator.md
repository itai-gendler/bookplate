---
kind: person
acts: external
references:
  - { kind: doc, role: intent, target: README.md, title: "README: Forgotten passwords and Reported showcases" }
  - { kind: code, role: implementation, target: scripts/reset-password.mjs }
  - { kind: code, role: implementation, target: scripts/remove-showcase.mjs }
---

# Server operator

Whoever runs the Bookplate server, with access to its configuration and to the
commands it ships for resetting a password and taking a showcase down.
