---
type: web
actors: [visitor, reader]
languages: [en]
entryPoints:
  - web: /
references:
  - { kind: code, role: implementation, target: app/layout.tsx }
  - { kind: code, role: implementation, target: components/AppBar.tsx }
  - { kind: code, role: implementation, target: proxy.ts }
---

# Bookplate web app

The web app every reader uses, installable on a phone's home screen. Signed
out, it offers signing in, first-run set-up, sign-up where registration is
open, password reset, and the public showcase and legal pages; signed in, the
Library, Vocabulary and Statistics sections and Settings.
