---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member picks a profile in the Profile picker
  kind: actor
  actor: household-member
  entities:
  - {entity: profile, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product keeps only the tasks that match every filter of the profile and none of its exclusions
  kind: product
  actor: household-member
  entities:
  - {entity: profile, effect: reads, facts: [Include, Labels, Areas, Devices, Companions, Exclude labels, Exclude areas, Exclude devices, Exclude companions, Exclude shopping]}
  - {entity: task, effect: reads, facts: [Due date, Labels, Area, Device, Managed by]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Filter the task list by a profile

## Trigger

A household member picks a saved profile on the Tasks tab.

## Outcome

Only the tasks the profile selects remain.
