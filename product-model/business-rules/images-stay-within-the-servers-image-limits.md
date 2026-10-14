---
appliesTo:
  - { type: capability, id: add-book }
  - { type: capability, id: edit-book }
  - { type: capability, id: edit-book-notes }
  - { type: capability, id: change-profile-photo }
  - { type: capability, id: find-covers }
  - { type: capability, id: import-library }
  - { type: entity, id: server-configuration, facts: [Image space limit, Largest image] }
references:
  - { kind: code, role: implementation, target: lib/limits.ts#checkStorage }
  - { kind: code, role: implementation, target: lib/limits.ts#tooLarge }
---

# An account's images stay within the server's image limits

No single cover or pasted image is larger than the server's largest image, and an account's covers, pasted images and profile photo together never take more than its image space. Images beyond either are refused with the reason.
