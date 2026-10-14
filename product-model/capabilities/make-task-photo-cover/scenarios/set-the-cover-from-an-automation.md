---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the set task photo cover action
  kind: actor
  actor: automation
  entities:
  - {entity: task-photo, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product makes it the cover
  kind: product
  actor: automation
  entities:
  - {entity: task-photo, effect: changes, facts: [Cover]}
  contexts:
    services: {place: services}
---

# Set the cover from an automation

## Trigger

An automation calls the set task photo cover action.

## Outcome

That photo is the cover.
