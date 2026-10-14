---
kind: primary
routes:
  card: Dashboard card
steps:
- text: The Household member presses + and fills the New task form
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    card: {place: dashboard-card}
- text: The Product creates the task and uploads its photos
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Notes, Schedule kind, Interval, Due date, Device, Area, Labels, On completion]}
  - {entity: task-photo, effect: creates, facts: [Image, Cover], with: task}
  contexts:
    card: {place: dashboard-card}
---

# Add a task from the dashboard card

## Trigger

A household member presses + on the card.

## Outcome

The new task is on the card.
