---
kind: primary
routes:
  panel: Panel
steps:
- text: On the periodic check a one-off task was completed more days ago than the retention
  kind: condition
  unattended: true
  entities:
  - {entity: task, effect: reads, facts: [Last completed]}
  - {entity: home-keeper-settings, effect: reads, facts: [One-off retention]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product deletes each such task
  kind: product
  entities:
  - {entity: task, effect: removes, from: Completed}
  - {entity: completion, effect: removes, with: task}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Delete completed one-off tasks after retention

## Trigger

The periodic check runs while One-off retention is above 0.

## Outcome

Completed one-off tasks older than the retention are gone.
