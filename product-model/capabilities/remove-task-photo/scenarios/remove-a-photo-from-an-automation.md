---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the remove task photo action
  kind: actor
  actor: automation
  entities:
  - {entity: task-photo, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product deletes the photo
  kind: product
  actor: automation
  entities:
  - {entity: task-photo, effect: removes}
  contexts:
    services: {place: services}
---

# Remove a photo from an automation

## Trigger

An automation calls the remove task photo action.

## Outcome

The photo is gone.
