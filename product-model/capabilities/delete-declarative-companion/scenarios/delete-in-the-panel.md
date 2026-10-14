---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Delete and confirms
  kind: actor
  actor: admin
  entities:
  - {entity: declarative-companion, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::companions'}
- text: The Product removes it with its tasks
  kind: product
  actor: admin
  entities:
  - {entity: declarative-companion, effect: removes, from: 'On'}
  - {entity: task, effect: removes, from: Monitored, with: declarative-companion}
  contexts:
    panel: {place: 'panel::administration::companions'}
---

# Delete a declarative companion in the panel

## Trigger

An admin presses Delete on its row.

## Outcome

It and its tasks are gone.

## Edge cases

- A profile that named it keeps it as Deleted declarative companion, which selects no task.
