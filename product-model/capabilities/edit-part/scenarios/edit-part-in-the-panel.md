---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses the Edit icon on a part and changes it
  kind: actor
  actor: admin
  entities:
  - {entity: part, effect: reads, facts: [Name, Replacement interval]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Admin presses Save
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product saves the part and updates the tasks it keeps
  kind: product
  actor: admin
  entities:
  - {entity: part, effect: changes, facts: [Name, Replacement interval, Action, Last replaced, Reorder at, Restock quantity, Auto-create buy task, NFC tag, Require tag scan, Attached file]}
  - {entity: task, effect: changes, facts: [Name, Interval, Due date, NFC tag, Require tag scan]}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Edit a part in the panel

## Trigger

An admin edits a part.

## Outcome

The part and its tasks have the new values.
