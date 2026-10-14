---
singleton: true
references:
  - { kind: code, role: implementation, target: lib/config.ts }
  - { kind: doc, role: intent, target: .env.example }
  - { kind: doc, role: intent, target: README.md, title: "README: Configuration" }
---

# Server configuration

The settings whoever runs the server chooses for the whole Bookplate, kept
once and read when the server starts.

## Information kept

- **Registration** — Closed, where only the first account can be made, or Open, where anyone who can reach the server can make one
- **Email** — whether the server can send email
- **Newsletter offered** — whether readers are offered a newsletter at sign-up and in Settings
- **Book limit** — the most books one library may hold, or no limit
- **Word limit** — the most words one vocabulary registry may hold, or no limit
- **Image space limit** — the most image space one account may use for covers, pasted images and its profile photo, or no limit
- **Largest image** — the largest single image a reader may store
- **Largest import** — the largest export zip or CSV a reader may import
- **Report address** — where a showcase's Report this page link writes to; without one the link is hidden
- **Privacy policy** — the server's privacy policy, as its own page or an address elsewhere, if it has one
- **Terms of use** — the server's terms of use, as its own page or an address elsewhere, if it has them
- **Owner account** — whether the first account, the owner's, has been made
