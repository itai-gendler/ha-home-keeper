---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member selects an appliance
  kind: actor
  actor: household-member
  entities:
  - {entity: appliance, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::appliance-list'}
- text: The Product opens its page with its details, parts, documents, tasks and maintenance history
  kind: product
  actor: household-member
  entities:
  - {entity: appliance, effect: reads, facts: [Manufacturer, Model, Serial number, Replacement cost, Custom fields, Related devices, Maintenance history]}
  - {entity: part, effect: reads, facts: [Name, Stock, Reorder at, Last replaced]}
  - {entity: appliance-document, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name, Due date]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Household member presses Open on a document
  kind: actor
  actor: household-member
  entities:
  - {entity: appliance-document, effect: reads, facts: [Name, File]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product opens the file through a link that expires within the hour
  kind: product
  actor: household-member
  entities:
  - {entity: appliance-document, effect: reads, facts: [File, Link]}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Open an appliance's page

## Trigger

A household member selects an appliance.

## Outcome

The household member reads the whole appliance record.

## Edge cases

- A user who is not an admin sees a View only chip and no Edit, Archive or Delete.
