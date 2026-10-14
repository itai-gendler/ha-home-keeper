---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member selects Print labels, selects appliances and presses Print
  kind: actor
  actor: household-member
  entities:
  - {entity: appliance, effect: reads, facts: [Name, Model]}
  contexts:
    panel: {place: 'panel::household::qr-labels'}
- text: The Product lays out a label for each appliance, and for each of its tasks when asked, with a code that links to its page
  kind: product
  actor: household-member
  entities:
  - {entity: appliance, effect: reads, facts: [Name, Model]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::qr-labels'}
---

# Print labels for appliances

## Trigger

A household member selects Print labels on the Appliances tab.

## Outcome

The browser's print dialog opens with one label per selected appliance.

## Edge cases

- Skip used labels starts on the next free label of a part-used sheet.
