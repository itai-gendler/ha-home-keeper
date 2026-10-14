---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update asset action without the part
  kind: actor
  actor: automation
  entities:
  - {entity: part, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product removes the part
  kind: product
  actor: automation
  entities:
  - {entity: part, effect: removes}
  contexts:
    services: {place: services}
---

# Remove a part from an automation

## Trigger

An automation calls the update asset action without the part.

## Outcome

The part is gone.
