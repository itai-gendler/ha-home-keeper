---
domain: appliances
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/assets.py
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# Create an appliance

Add an appliance as a new virtual device that its tasks share, or add the same record to an existing device another integration provides.
