---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin picks a preset, such as Firmware update available
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::companions'}
- text: The Admin reviews the preview, excludes an entity and saves
  kind: actor
  actor: admin
  entities:
  - {entity: declarative-companion, effect: reads, facts: [Name, Exclusions]}
  contexts:
    panel: {place: 'panel::administration::declarative-companion'}
- text: The Product saves the declarative companion and opens a monitored task for each matching entity, due now where the condition holds
  kind: product
  actor: admin
  entities:
  - {entity: declarative-companion, effect: creates, to: 'On', facts: [Name, Description, Target integration, Entity filters, Entity keys, Exclusions, Trigger mode, Trigger condition, Task name template, Task notes template, Task labels, Auto-clear]}
  - {entity: task, effect: creates, to: Monitored, facts: [Name, Notes, Schedule kind, Sensor, Labels, Managed by, Completed by its condition], with: declarative-companion}
  contexts:
    panel: {place: 'panel::administration::declarative-companion'}
---

# Add a declarative companion from a preset

## Trigger

An admin picks a preset in Add from preset.

## Outcome

The declarative companion is on and opens a task for each matching entity whose condition holds.

## Edge cases

- A warning shows above 50 matches.
- A declarative companion that would match more than 500 entities is refused.
- A template that cannot render shows its error in the preview.
