---
kind: configuration
of: capability-scenario
settings:
  - { entity: server-configuration, fact: Email }
takesEffect: When the server starts; the forgot-password page reads it each time it opens.
stability: A change to the server's email settings applies after a restart. Reset links already sent work until they expire.
alternatives:
  - id: reset-a-forgotten-password
    selectedWhen: The server can send email.
  - id: reset-password-without-email
    selectedWhen: The server has no email set up, the default.
references:
  - { kind: code, role: implementation, target: app/forgot-password/page.tsx }
  - { kind: code, role: implementation, target: lib/config.ts }
---

# Password reset by email

A server with email lets readers reset a forgotten password themselves; one
without email leaves it to whoever runs the server. Both are supported, since
email is optional.
