---
type: cli
actors: [server-operator]
references:
  - { kind: code, role: implementation, target: scripts/reset-password.mjs }
  - { kind: code, role: implementation, target: scripts/remove-showcase.mjs }
  - { kind: doc, role: intent, target: README.md, title: "README: Forgotten passwords and Reported showcases" }
---

# Server commands

The commands Bookplate ships for whoever runs the server, run inside its
container: resetting an account's password and taking a reported showcase
down.
