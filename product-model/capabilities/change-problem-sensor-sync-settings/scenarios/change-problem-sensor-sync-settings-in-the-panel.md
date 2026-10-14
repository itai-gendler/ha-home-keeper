---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin turns on Problem sensor sync and excludes a device
  kind: actor
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: reads, facts: [Problem sensor sync, Problem sensor exclusions]}
  contexts:
    panel: {place: 'panel::administration::settings'}
- text: The Product saves the change at once and applies it
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Problem sensor sync, Problem sensor exclusions]}
  contexts:
    panel: {place: 'panel::administration::settings'}
---

# Change the problem sensor sync settings in the panel

## Trigger

An admin opens Settings.

## Outcome

Each problem sensor that is not excluded has a task that arms while it reports a problem.
