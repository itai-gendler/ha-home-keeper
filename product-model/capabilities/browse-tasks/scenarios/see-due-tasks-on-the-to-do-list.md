---
kind: primary
routes:
  entities: Native entities
steps:
- text: The Household member opens the Home Keeper to-do list
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    entities: {place: native-entities}
- text: The Product shows each enabled task that has a due date as an item with its due date and notes
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name, Due date, Notes]}
  contexts:
    entities: {place: native-entities}
- text: The Product shows each scheduled clock task on the calendar at its next due date
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name, Due date, Notes]}
  contexts:
    entities: {place: native-entities}
---

# See due tasks on the to-do list and the calendar

## Trigger

A household member opens the Home Keeper to-do list or calendar in Home Assistant.

## Outcome

The to-do list holds the due tasks and the calendar holds the upcoming scheduled tasks.

## Edge cases

- The calendar never shows a triggered or sensor-based task, armed or not.
