---
domain: appliances
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/store.py#HomeKeeperStore
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# Adjust part stock

Move a part's spare stock up or down by hand, with the In stock stepper or the adjust part stock action. Low-stock events and buy tasks follow, as for a completion.
