---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update asset action with the changed part
  kind: actor
  actor: automation
  entities:
  - {entity: part, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product saves the part
  kind: product
  actor: automation
  entities:
  - {entity: part, effect: changes, facts: [Reorder at, Restock quantity]}
  contexts:
    services: {place: services}
---

# Edit a part from an automation

## Trigger

An automation calls the update asset action with a changed part.

## Outcome

The part and its tasks have the new values.
