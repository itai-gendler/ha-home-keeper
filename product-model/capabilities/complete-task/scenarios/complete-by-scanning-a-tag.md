---
kind: primary
routes:
  tags: NFC tags
steps:
- text: The Household member scans the tag on the item
  kind: actor
  actor: household-member
  entities: []
  contexts:
    tags: {place: nfc-tags}
- text: The Product completes each enabled task linked to the tag
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    tags: {place: nfc-tags}
---

# Complete a task by scanning its tag

## Trigger

A household member scans an NFC tag.

## Outcome

Each enabled task linked to the tag is completed.

## Edge cases

- A disabled task is not completed by a scan.
