---
domain: profile
availability:
  - { place: server-commands }
references:
  - { kind: code, role: implementation, target: scripts/remove-showcase.mjs }
  - { kind: doc, role: intent, target: README.md, title: "README: Reported showcases" }
---

# Take down a showcase

Remove a reported showcase from the server by its link, leaving the reader's
library untouched.
