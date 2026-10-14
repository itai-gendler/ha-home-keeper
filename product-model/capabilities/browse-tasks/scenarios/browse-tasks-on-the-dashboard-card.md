---
kind: primary
routes:
  card: Dashboard card
steps:
- text: The Household member opens a dashboard that holds the card
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    card: {place: dashboard-card}
- text: The Product lists the tasks that match the card's status, area, device, label, schedule kind or profile filter, with the cover photo of each task
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name, Due date, Schedule kind, Area, Device, Labels, Notes]}
  - {entity: task-photo, effect: reads, facts: [Image, Cover]}
  - {entity: profile, effect: reads, facts: []}
  contexts:
    card: {place: dashboard-card}
---

# Browse tasks on the dashboard card

## Trigger

A household member opens a dashboard with the Home Keeper Tasks card.

## Outcome

The card lists the tasks its filter selects, grouped and sorted as configured.

## Edge cases

- With Hide card when empty, a card whose filter matches no task is not shown; else it says that no task matches.
