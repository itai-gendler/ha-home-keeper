---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin turns off Enabled and saves
  kind: actor
  actor: admin
  entities:
  - {entity: declarative-companion, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::declarative-companion'}
- text: The Product switches it off and disables its tasks
  kind: product
  actor: admin
  entities:
  - {entity: declarative-companion, effect: changes, from: 'On', to: 'Off', facts: []}
  - {entity: task, effect: changes, from: Monitored, to: Disabled, facts: []}
  contexts:
    panel: {place: 'panel::administration::declarative-companion'}
---

# Switch a declarative companion off

## Trigger

An admin turns off Enabled.

## Outcome

Its tasks stay with their history and stop.
