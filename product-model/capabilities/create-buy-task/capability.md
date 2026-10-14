---
availability:
- {place: 'panel::household'}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/reconcile.py#reconcile_buy_tasks
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# Create a buy task

When the stock of a part with Auto-create buy task drops to or below its reorder threshold, Home Keeper adds one Buy task for it, in the Shopping section and on the to-do list. Restocking the part another way removes it.
