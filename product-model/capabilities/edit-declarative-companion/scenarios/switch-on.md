---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin turns on Enabled and saves
  kind: actor
  actor: admin
  entities:
  - {entity: declarative-companion, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::declarative-companion'}
- text: The Product switches it on and enables the tasks it stopped
  kind: product
  actor: admin
  entities:
  - {entity: declarative-companion, effect: changes, from: 'Off', to: 'On', facts: []}
  - {entity: task, effect: changes, from: Disabled, to: Monitored, facts: []}
  contexts:
    panel: {place: 'panel::administration::declarative-companion'}
---

# Switch a declarative companion on

## Trigger

An admin turns on Enabled.

## Outcome

Its tasks start again.
