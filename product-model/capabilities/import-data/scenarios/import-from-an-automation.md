---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the import data action with a bundle name
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product imports the records
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Schedule kind]}
  contexts:
    services: {place: services}
---

# Import from an automation

## Trigger

An automation calls the import data action.

## Outcome

The records are imported, or only previewed with dry run.
