---
appliesTo:
  - type: entity
    id: reader
    effect: removes
permits:
  - self: true
  - unattended: true
    when:
      - { fact: Email confirmed, is: No }
references:
  - { kind: code, role: implementation, target: app/api/account/route.ts }
  - { kind: code, role: implementation, target: lib/housekeeping.ts#removeUnverifiedAccounts }
---

# An account is deleted only by its reader, or by the Product when it was never confirmed

A Reader deletes their own account and nobody else's. The Product removes an account on its own only when it never confirmed its address where that is required.
