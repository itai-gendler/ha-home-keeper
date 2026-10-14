---
appliesTo:
- type: entity
  id: part
  effect: changes
  facts:
  - Stock
  - Last replaced
  contexts:
  - {place: 'panel::household::task'}
  - {place: 'panel::household::task-list'}
  - {place: dashboard-card}
  - {place: native-entities}
  - {place: mobile-notifications}
  - {place: nfc-tags}
permits:
- actors:
  - household-member
  - admin
  - automation
  - companion
- unattended: true
references:
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# Any signed-in user's completion draws or restocks a part's stock

Completing a task that uses a part draws its stock and sets its last replaced date, and completing a buy task restocks the part, on every surface where tasks are completed.
