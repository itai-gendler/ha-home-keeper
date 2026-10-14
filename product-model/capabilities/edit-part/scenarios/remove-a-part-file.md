---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin removes the attached file and confirms
  kind: actor
  actor: admin
  entities:
  - {entity: part, effect: reads, facts: [Attached file]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product deletes the stored file
  kind: product
  actor: admin
  entities:
  - {entity: part, effect: changes, facts: [Attached file]}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Remove a part's attached file

## Trigger

An admin removes the file of a part.

## Outcome

The file is gone.
