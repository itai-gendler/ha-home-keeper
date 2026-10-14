---
availability:
- {place: 'panel::household'}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/shopping_sync.py#ShoppingListSync
- kind: code
  role: implementation
  target: custom_components/home_keeper/shopping.py#plan_sync
---

# Sync buy tasks to the shopping list

Keep every open Buy task as an item on the to-do list chosen as the shopping list, with the amount to buy, both ways: a checked item completes the Buy task and restocks the part.
