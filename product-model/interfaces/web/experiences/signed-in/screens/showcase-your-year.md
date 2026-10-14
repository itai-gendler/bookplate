---
entities:
  - { entity: showcase, shows: [Year, Books to show, Name on the page, Link], collects: [Year, Books to show, Name on the page] }
  - { entity: reader, shows: [Name] }
references:
  - { kind: code, role: implementation, target: components/ShowcaseDialog.tsx }
---

# Showcase your year

Where a reader makes, changes or turns off the showcase of one year, and
copies or opens its link.
