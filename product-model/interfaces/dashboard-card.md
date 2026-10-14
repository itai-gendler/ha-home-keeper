---
type: web
actors:
- admin
- household-member
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/card.ts
- kind: code
  role: implementation
  target: custom_components/home_keeper/card.py
- kind: doc
  role: intent
  target: docs/guide/views/dashboard-card.md
---

# Dashboard card

The Home Keeper Tasks card that any dashboard can hold. It lists the tasks a card filter selects,
completes, snoozes and skips them, and adds new tasks with photos.
