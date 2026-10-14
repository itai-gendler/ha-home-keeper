---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin sets the unit to uses, a target, the word for a use and a time limit, and saves
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product adds the part with a use task that is never due and a replacement task that is due once the count reaches the target
  kind: product
  actor: admin
  entities:
  - {entity: part, effect: creates, facts: [Name, Kind, Count uses as, Use task name, Target uses, Time limit]}
  - {entity: task, as: use-task, effect: creates, to: Counted, facts: [Name, Schedule kind], with: part}
  - {entity: task, as: replacement-task, effect: creates, to: Monitored, facts: [Name, Schedule kind], with: part}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Add a wear item that counts uses

## Trigger

An admin sets a wear item's unit to uses with a target.

## Outcome

A use task and a replacement task exist.

## Edge cases

- A target above 250 uses is refused.
