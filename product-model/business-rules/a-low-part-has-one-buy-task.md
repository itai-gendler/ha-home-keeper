---
appliesTo:
- type: capability
  id: create-buy-task
- type: capability
  id: complete-task
- type: capability
  id: sync-shopping-list
references:
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# A part that runs low has exactly one buy task

While a part with Auto-create buy task is at or below its reorder threshold there is one Buy task for it; completing it restocks the part by its restock quantity, and the task stays while the stock remains low.
