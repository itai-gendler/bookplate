---
appliesTo:
  - { type: capability, id: view-statistics }
  - { type: capability, id: browse-library }
references:
  - { kind: code, role: implementation, target: lib/ratings.ts#averageRating }
---

# Average ratings and the ratings chart count only rated books read to the end

A rating on a Book still being read, waiting on the shelf or given up stays out of every average rating and out of Ratings given; so does an unrated Book.

## Rationale

Only a book read to the end has had a verdict on the whole of it.
