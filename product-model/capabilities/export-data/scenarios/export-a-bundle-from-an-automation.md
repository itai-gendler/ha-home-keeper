---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the export data action with kind bundle
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product writes the dated zip file with the YAML file and the files, replacing one from the same day, and returns its path and size
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: task-photo, effect: reads, facts: [Image]}
  - {entity: appliance-document, effect: reads, facts: [File]}
  contexts:
    services: {place: services}
---

# Export a bundle from an automation

## Trigger

An automation calls the export data action with kind bundle.

## Outcome

The bundle is in the exports folder.
